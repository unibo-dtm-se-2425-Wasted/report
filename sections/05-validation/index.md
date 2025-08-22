---
title: Validation
has_children: false
nav_order: 6
---

# Validation

## Testing approach

The testing approach in this project focused mainly on **unit testing**, to validate both application logic and database operations in isolation.  
The project did not explicitly follow Test-Driven Development (TDD), but tests were written alongside feature implementation to ensure correctness and reliability.

The testing framework used is **`unittest`**, as it is included in the Python standard library, provides a clear structure for organizing tests, and integrates easily with Python projects.

## Testing (automated)

### Unit testing

Unit tests were developed to validate individual functions and methods, especially for:

- **Application logic:** Testing the `calculate_statistics` function to ensure correct computation of totals, expired items, and valid items in a DataFrame.  
- **Database operations:** Ensuring correct insertion and retrieval of food items, including edge cases such as zero quantity.  

Unit tests were developed to validate individual functions and methods, especially for:

- **Database operations:** Ensuring correct insertion and retrieval of food items, including edge cases such as zero quantity.  
- **Application logic:** Testing functions like `calculate_statistics` to ensure correct computation of totals, expired items, and valid items in a DataFrame.  

**Rationale:** Unit tests ensure that core functions work as expected in isolation, reducing the risk of bugs propagating through the system.  

**Success rate and coverage:**  
- Success rate: 100% of executed tests passed.  
- Approximate coverage: 85% of backend logic, including database handling and app logic, but excluding Streamlit UI interactions.

### Integration testing
Integration tests focused on **database operations combined with application logic**, for example:

- Inserting data into the database and retrieving it to ensure consistency.  
- Running statistics calculations on retrieved data to verify end-to-end correctness.  

**Rationale:** Ensures that different components (database + application functions) interact correctly.  

**Success rate:** 100%  
**Coverage:** Covers database and logic integration, no external services tested.  

**Test doubles:** None were used, as SQLite test database served as an isolated environment for integration testing.

### System testing

System tests were not fully automated, but the combination of database unit tests and app logic unit tests effectively validates the system behavior at a small-scale level.


## Acceptance tests (manual)

Manual testing was performed to validate the system as a whole:

- Adding, modifying, and deleting food items through the UI to ensure proper interaction with the backend.  
- Checking that statistics displayed on the app correspond correctly to database contents.  

**Test rationale:** Matches the expected user scenarios and functional requirements.  
**Success rate:** All acceptance tests passed successfully.
ying, and deleting food items through the UI to ensure proper interaction with the backend.  
- Checking that statistics displayed on the app correspond correctly to database contents.  

**Rationale:** These tests match the main functional requirements and replicate expected user interactions.  

**Success rate:** All acceptance tests passed successfully.  

## Future improvements

To strengthen validation, the following improvements are planned:  
- Add **integration tests** combining database and app logic.  
- Extend unit tests to cover **edge cases** (invalid dates, empty fields, unsupported units).  
- Develop **system-level tests** to automatically check end-to-end functionality.  
- Evaluate **performance testing** to measure scalability with larger datasets.  
