# Validation Report

## Testing Approach

The testing strategy for this project primarily relies on unit testing to validate core application logic and database interactions in isolation. The project does not strictly adhere to Test-Driven Development (TDD) but ensures that tests are written alongside new features to confirm their correctness and reliability.

The `unittest` framework, a standard library in Python, was chosen for its clear structure, ease of use, and seamless integration with the project.

## Automated Testing

### Unit Testing

Unit tests were developed to validate individual functions and methods, with a strong focus on two main areas:

- **Application logic**: Validating the `calculate_statistics` function to ensure accurate computation of metrics such as total items, expired items, and valid items from a DataFrame.

- **Database operations**: Comprehensive testing of database functions to guarantee correct insertion, retrieval, and management of data. This now includes:
  - **Food items**: Ensuring proper handling of food items, including edge cases like zero quantity. The test `test_insert_zero_quantity` specifically verifies that a food item can be stored even with a quantity of 0.
  - **User authentication**: A new suite of tests was added to validate user management functions, including `add_user` and `check_user_credentials`. These tests cover successful user creation and login, as well as failure scenarios such as incorrect passwords (`test_add_and_login_user`) and attempts to create duplicate users (`test_duplicate_user`). The use of a temporary in-memory database for these tests ensures a clean state for each test run, isolating them from the main application database.

**Rationale:** Unit tests are crucial for verifying that individual components function as intended in a controlled environment. This approach significantly reduces the risk of bugs and simplifies debugging by pinpointing the exact source of an issue.

#### Success Rate and Coverage

- **Success Rate** 

  Approximately **88–90%** of automated tests passed successfully across different environments:  
  - Most unit tests for database operations and statistics ran reliably;  
  - Occasional failures occurred in CI (GitHub Actions) due to differences in environment setup or test assumptions;  
  - Some tests needed to be adjusted or rewritten when run locally in VSCode to ensure stability.  

- **Coverage** 

  The tests provide solid coverage of the core backend logic, including database handling for both food items and user management, along with the application's statistical calculations.  
  The Streamlit UI and external dependencies are not covered by these tests.

### Integration and System Testing

While dedicated automated integration and system tests were not developed, their functionality was indirectly validated. Unit tests for database operations and application logic, combined with manual acceptance testing, confirm that the main components (UI, database, and backend logic) interact as expected.

### Manual Acceptance Testing

Manual testing was conducted to validate the application from an end-user perspective. These tests focused on key functional requirements and user scenarios:

- **User interactions:**
  - Adding, modifying, and deleting food items through the UI.
  - Creating new users and logging in with both correct and incorrect credentials.
- **Data integrity:** Verifying that the statistics displayed in the application's UI accurately reflect the data stored in the database.

**Rationale:** This manual validation ensures the system's overall usability and that it meets the user's expectations in a real-world scenario.


