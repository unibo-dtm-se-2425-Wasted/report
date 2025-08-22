---
title: Validation
has_children: false
nav_order: 6
---

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

**Rationale:** Unit tests ensure that core functions work as expected in isolation, reducing the risk of bugs propagating through the system.  

**Success rate and coverage:**  
- Success rate: 100% of executed tests passed.  
- Coverage: core backend logic, including database handling and app statistics calculation. Streamlit UI interactions were not covered.  

### Integration testing
Dedicated integration tests were not implemented.  
However, the unit tests on database functions and the app logic, combined with manual acceptance testing, already validated that the two main components work as intended. A future improvement would be adding automated tests that insert data into the database and directly compute statistics on the retrieved data.

### System testing

No automated system tests were developed.  
System behavior was indirectly validated through the combination of unit tests and manual acceptance testing. In future iterations, automated system tests matching the acceptance criteria would improve validation coverage.

## Acceptance tests (manual)

Manual testing was performed to validate the system as a whole, focusing on user scenarios:  

- Adding, modifying, and deleting food items through the UI to ensure proper interaction with the backend.  
- Checking that statistics displayed on the app correspond correctly to database contents.  

**Rationale:** These tests match the main functional requirements and replicate expected user interactions.  

**Success rate:** All acceptance tests passed successfully.  

## Future improvements

To strengthen validation, the following improvements are planned:  
- Add **integration tests** combining database and app logic.  
- Extend unit tests to cover **edge cases** (invalid dates, empty fields, unsupported units).  
- Develop **system-level tests** to automatically check end-to-end functionality.  
- Evaluate **performance testing** to measure scalability with larger datasets.  
