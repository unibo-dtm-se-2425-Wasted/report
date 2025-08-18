---
title: Requirements
has_children: false
nav_order: 3
---

# Requirements

## User stories

To identify key personas and their activities, we defined the following user stories:

### Persona 1: Michela (health and environmentally - conscious student)
- *As a student with limited budget, I want notifications for expiring items, so I can avoid unnecessary waste.*
- *As a health-conscious person, I want to filter my pantry by food category (vegetables, meat, etc.), so I can check what I still have before shopping.*
- *As an environmentally-conscious user, I want to see statistics about how much food I wasted or saved, so I can improve my habits.*

### Persona 2: Fred (parent)
- *As a busy parent, I want to keep track of the food in my fridge, so I don’t accidentally let products expire and waste money.*
- *As a parent, I want to see which items are about to expire, so I can plan meals around them.*
- *As a parent, I want recipe suggestions based on soon-to-expire food, so I can quickly decide what to cook.*

---

## Requirements analysis

- The application will help users manage their pantry or fridge contents efficiently, reduce food waste, and promote sustainable consumption habits.

---
### Functional requirements (FR)

| Title                                   | Requirement                                                                                          | Acceptance Criteria                                                                                          |
|-----------------------------------------|------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| **Add food items**                         | The system shall allow users to add food items with details: name, category, purchase & expiry dates, quantity, and unit. | Users can successfully input all required data into a form and save it.                                      |
| **Display food dashboard**                 | The system shall display all stored food items on a dashboard, sorted by the date they were added.           | Users see an organized list of food.                                    |
| **Highlight soon-to-expire items**         | The system shall visually highlight items close to expiry ( within 3 days) in yellow and the expired ones in red.             | Items nearing expiry or expired are clearly marked  on the dashboard.                                             |
| **in-app notifications**        | The system shall notify users when adding ore deleting food items through visual alerts. | Users receive notifications inside the app and optionally via push notifications (if enabled).               |
| **Recipe suggestions**                     | The system shall suggest recipes based on the ingredients that are about to expire.                 | Users can view a list of recipes where most ingredients are about to expire.                                |
| **Waste statistics and insights**          | The system shall track expired vs consumed items and display waste statistics (e.g., % of wasted items, estimated cost). | Users can view waste statistics in the app showing trends and data visualizations.                          |
| **Filter by food status**          | The user can filter the list by the food item’s status (OK, Expiring Soon, Expired). |  The system shall provide a Filter section in the sidebar, allowing users to narrow down the displayed list of food items based on selected criteria.                         |
---
### Non-functional requirements (NFR)

| Title                                    | Requirement                                                                                               | Acceptance Criteria                                  |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| **Responsive user interface**               | The system shall provide a user-friendly and responsive interface accessible from desktop and mobile devices. | The UI displays correctly on common screen sizes.    |
| **Offline data storage**            | The system shall store data locally using a lightweight database to ensure offline functionality.        | Users can use the core app features without internet.|
| **AI API reliability**	|The system should handle failures or downtime of the external AI API gracefully.|	If the API is unavailable, the system shows a user-friendly error and falls back (e.g., no suggestions).|
| **API latency**	|The system should handle AI API responses within 3 seconds to avoid a poor user experience.|	The average API call response time must not exceed 3 seconds.|

---

### Implementation constraints (IC)

| Title                                | Constraint                                                                                                 | Justification                                                                                     |
|--------------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Backend framework constraint**         | Backend and frontend are integrated and built using Python with Streamlit.                                                  | To enable rapid development and direct UI integration.                                        |
| **Database and cloud services**          | The database uses a local SQLite file, ensuring persistent data storage without requiring external servers.           | SQLite is lightweight for local use  |
| **Frontend technology stack**            | The interface is dynamically generated using Streamlit components.           | It ensures accessibility and simplicity      |
| **External API usage** | The system must integrate with a third-party AI API (Spooncular), to implement recipe suggestions.| Developing an in-house recipe engine is outside the scope and requires massive domain knowledge and datasets. |

---

### Glossary

| Term                 | Definition                                                                                     |
|----------------------|-------------------------------------------------------------------------------------------------|
| **Food item**        | A product stored by the user, with metadata (name, category, dates, quantity, unit).           |
| **Dashboard**        | The main screen where all stored food items are listed and managed.                            |
| **Soon-to-expire**   | A food item that will expire within a pre-defined time window (3 days).                  |
| **Recipe suggestion**| A feature that matches soon-to-expire ingredients with predefined recipes.                     |
| **Waste statistics** | A module that tracks expired and consumed food to calculate waste percentages and costs.       |
| **Expiry date** | The date after which a food item is considered expired.       |
---