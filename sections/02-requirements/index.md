---
title: Requirements
has_children: false
nav_order: 3
---

# Requirements

## User stories

To identify key personas and their activities, we defined the following user stories:

### Persona 1: Michela (Health and Environmentally - Conscious Student)
- *As a student with limited budget, I want notifications for expiring items, so I can avoid unnecessary waste.*
- *As a health-conscious person, I want to filter my pantry by food category (vegetables, meat, etc.), so I can check what I still have before shopping.*
- *As an environmentally-conscious user, I want to see statistics about how much food I wasted or saved, so I can improve my habits.*

### Persona 2: Fred (Parent)
- *As a busy parent, I want to keep track of the food in my fridge, so I don’t accidentally let products expire and waste money.*
- *As a parent, I want to see which items are about to expire, so I can plan meals around them.*
- *As a parent, I want recipe suggestions based on soon-to-expire food, so I can quickly decide what to cook.*

---

## Requirements analysis

- The application will help users manage their pantry or fridge contents efficiently, reduce food waste, and promote sustainable consumption habits.

---
### Functional Requirements (FR)

| Title                                   | Requirement                                                                                          | Acceptance Criteria                                                                                          |
|-----------------------------------------|------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| **Add Food Items**                         | The system shall allow users to add food items with details: name, category, purchase & expiry dates, quantity, and unit. | Users can successfully input all required data into a form and save it.                                      |
| **Display Food Dashboard**                 | The system shall display all stored food items on a dashboard, sorted by expiration date.           | Users see an organized list where items nearing expiry appear at the top.                                    |
| **Highlight Soon-to-Expire Items**         | The system shall visually highlight items close to expiry (e.g., within 3 days) in red.             | Items nearing expiry are clearly marked in red on the dashboard.                                             |
| **Filter and Search Food Items**           | The system shall allow filtering and searching of food items by category, product name, or expiry date. | Users can use dropdown filters or search bars to narrow down the list of food items.                        |
| **Notifications for Expiring Food**        | The system shall notify users about soon-to-expire food items through visual alerts and/or push notifications. | Users receive notifications inside the app and optionally via push notifications (if enabled).               |
| **Recipe Suggestions**                     | The system shall suggest recipes based on the ingredients that are about to expire.                 | Users can view a list of recipes where most ingredients are about to expire.                                |
| **Waste Statistics and Insights**          | The system shall track expired vs consumed items and display waste statistics (e.g., % of wasted items, estimated cost). | Users can view waste statistics in the app showing trends and data visualizations.                          |

---
### Non-Functional Requirements (NFR)

| Title                                    | Requirement                                                                                               | Acceptance Criteria                                  |
|------------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| **Responsive User Interface**               | The system shall provide a user-friendly and responsive interface accessible from desktop and mobile devices. | The UI displays correctly on common screen sizes.    |
| **Offline Data Storage  (????)**            | The system shall store data locally using a lightweight database to ensure offline functionality.        | Users can use the core app features without internet.|
| **Reliable Notifications**                  | Notifications (if implemented with Firebase) shall be sent in a timely and reliable manner.              | Notifications appear within 1 minute of expiry check.|
| **AI API Reliability**	|The system should handle failures or downtime of the external AI API gracefully.|	If the API is unavailable, the system shows a user-friendly error and falls back (e.g., no suggestions).|
| **API Latency**	|The system should handle AI API responses within 3 seconds to avoid a poor user experience.|	The average API call response time must not exceed 3 seconds.|

---

### Implementation Constraints (IC)

| Title                                | Constraint                                                                                                 | Justification                                                                                     |
|--------------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Backend Framework Constraint**         | The backend shall be implemented using Python with Flask.                                                  | Chosen due to team familiarity and lightweight deployment.                                        |
| **Database and Cloud Services**          | The database shall use SQLite for local storage and Firebase for optional notification delivery.           | SQLite is lightweight for local use; Firebase allows easy cloud integration for notifications.   |
| **Frontend Technology Stack**            | The frontend shall be developed using HTML and CSS (with optional JavaScript for interactivity).           | HTML/CSS ensures accessibility and simplicity; fits professor’s requirements for tech stack.     |
| **External API Usage** | The system must integrate with a third-party AI API (e.g., Gemini, GPT, or similar), to implement recipe suggestions.| Developing an in-house recipe engine is outside the scope and requires massive domain knowledge and datasets. |

---

### Glossary

| Term                 | Definition                                                                                     |
|----------------------|-------------------------------------------------------------------------------------------------|
| **Food Item**        | A product stored by the user, with metadata (name, category, dates, quantity, unit).           |
| **Dashboard**        | The main screen where all stored food items are listed and managed.                            |
| **Soon-to-Expire**   | A food item that will expire within a pre-defined time window (e.g., 3 days).                  |
| **Recipe Suggestion**| A feature that matches soon-to-expire ingredients with predefined recipes.                     |
| **Waste Statistics** | A module that tracks expired and consumed food to calculate waste percentages and costs.       |

---