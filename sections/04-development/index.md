---
title: Development
has_children: false
nav_order: 5
---

# Development

## DVCS

The code was developed using a Distributed Version Control System (DVCS), specifically Git.  
This enabled the team to track changes in the repository in a collaborative and granular way, ensuring that each contribution was clearly documented. 

**Branching conventions:**  
The project followed a branch-based workflow inspired by Git Flow.  
A `main` branch was used for stable, production-ready code, while new features and improvements were implemented in dedicated branches, one for each group member.  
Once completed and tested, these branches were merged into `main` after a code review process.

**Conventions for commits:**  
Commits were made following a clear and descriptive format to maintain a clean history of changes.  
Each commit contained a short description of the modification made, for example 'added delete option', 'corrected expiration date status check logic'

**Any other relevant aspect:**  
Using Git allowed the team to work independently according to their individual expertise, reducing merge conflicts.  
At the end of the development cycle, all modules were reviewed together to ensure quality, consistency, and integration between different parts of the application. 

## Implementation details

During development, we deepened our knowledge of Streamlit as a framework for creating interactive web applications directly in Python.  
We also integrated Plotly and Pandas for dynamic data visualization, improving the presentation of food status statistics.  
Another relevant learning point was interacting with an external API (Spoonacular) to provide real-time recipe suggestions based on items nearing expiration.  
This experience improved our understanding of HTTP requests with the `requests` library, handling JSON responses, and integrating third-party data sources seamlessly.  
  
One of the most valuable components is the `check_status` function, which automatically evaluates the expiration status of each item and assigns it a clear visual label ("✅ OK", "⚠️ Expiring Soon", "❌ Expired").  
Although simple in logic, this function is central to the application’s usability, as it allows users to quickly assess the state of their food and take timely action to reduce waste.  

Its design makes it easy to extend — for example, adding configurable thresholds for “Expiring Soon” or integrating price-based loss calculations — showing how thoughtful implementation supports future growth.  

**Network protocols:**  
- HTTP/HTTPS is used for requests to the Spoonacular API via the `requests` library.  
- HTTPS ensures encryption of data in transit, protecting the API key and any sensitive information exchanged.    

**In-transit data representation:**  
- JSON is used for communication with the Spoonacular API.  
- It is widely supported, human-readable, and easily converted into Python dictionaries or Pandas DataFrames.  

**Database querying:**  
- SQLite is used for data persistence, managed through the `sqlite3` module.  
- Chosen for its simplicity, portability, and zero-configuration setup, ideal for local applications and prototypes.  

**Authentication:**  
- API Key authentication is used for accessing the Spoonacular API.  
- No internal authentication between components is implemented, as the app is designed for single-user use.  
 
## Technological details

**Programming languages, frameworks, libraries, and tools:**  
- **Python**: Main programming language for backend logic and data handling due to its simplicity and rich ecosystem.  
- **Streamlit**: Used for creating an interactive web interface directly in Python, allowing rapid prototyping and deployment.  
- **Plotly Express**: For dynamic and interactive data visualizations, such as pie charts and status indicators.  
- **SQLite**: Lightweight database for storing user data and food items, chosen for its simplicity and portability.  
- **Requests**: Python library for handling HTTP requests to external APIs.  
- **Datetime & Pandas**: For date handling, calculations, and data manipulation.

**Libraries the project depends on:**  
- `streamlit`: To build the frontend and interactive interface.  
- `plotly`: For visualization of food status and statistics.  
- `requests`: To interact with the Spoonacular API.  
- `pandas`: For data manipulation and filtering.  
- `sqlite3` (Python standard library): For managing the database.

**External technology or service dependencies:**  
- **Spoonacular API**: Provides recipe suggestions based on ingredients that are about to expire, enabling personalized and dynamic content for the user.  
- **HTTPS/JSON**: Used for secure data exchange with external services.  