---
title: Validation
has_children: false
nav_order: 6
---

# Validation

## Testing approach

The testing approach followed in this project combined unit testing to validate individual functions and methods with isolated data, and integration checks where database operations and app logic interact. The project did not explicitly follow Test-Driven Development (TDD), but tests were written alongside feature implementation to ensure correctness and reliability.

The testing framework used is **`unittest`** because it is included in the Python standard library, provides a clear structure for writing and organizing tests, and integrates easily with Python projects.

## Testing (automated)

> General recommendation: when discussing the tests below, please track to which requirement each test is related to.

### Unit testing

- Describe the unit tests you developed, and their rationale
- Report success rate and test coverage here

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

- Describe couples of components that you tested together, and the corresponding test rationale/plan

- Report success rate and test coverage here

- If you used [test doubles](https://en.wikipedia.org/wiki/Test_double), describe her which type of double you used, and why

### System testing

- Describe the tests that you developed to automatically test the system as a whole
    + and the corresponding test rationale/plan
    + better would be to have system tests that match the acceptance criteria of the requirements

- Report success rate and test coverage here

- If you adopted containers (e.g. Docker compose) for testing, describe how you used them here
    + e.g. to run the system in a clean environment, or to run the tests in a clean environment

## Acceptance tests (manual)

- If you did any manual testing, describe it here
- Report the test rationale/plan so that another person can repeat the tests
    + better would be for acceptance tests to match the acceptance criteria of the requirements
- Report success rate here

