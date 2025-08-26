---
title: CI/CD
has_children: false
nav_order: 9
---

# CI/CD

## Conceptual description

The project exploits a **Continuous Integration / Continuous Delivery (CI/CD)** workflow based on **GitHub Actions**.  
The purpose of the workflow is to ensure that the system remains stable and correct at every commit, by automatically executing the defined test suite.  

### Scope of Automation
---
**Continuous Integration (CI):**  
  - Every push and pull request on the main branch automatically triggers the workflow.  
  - The workflow installs dependencies and runs all unit tests.  
  - If tests fail, the workflow is marked as failed and contributors are notified by email.  

**Continuous Delivery (CD):**  
  - At this stage, no deployment automation is implemented.  
  - However, the project is structured so that adding a deployment step (e.g., building a Docker image or deploying to a hosting service) would be straightforward.

The rationale for this automation is to ensure that new contributions do not compromise existing functionality, while also enforcing a baseline of code quality by requiring that all tests pass before merging. It further provides developers with immediate feedback through GitHub’s notifications and status checks, which shortens response times and promotes safer, more efficient collaboration.

### Implementation Details
GitHub Actions uses a YAML configuration file (placed in `.github/workflows/`) that specifies:  
  - The **trigger** (push, pull request).  
  - The **environment** (Python version).  
  - The **jobs** (install dependencies, run tests).  
Tests are executed in a clean virtual environment provided by GitHub runners.  

## Current status

- The CI workflow is active and working: contributors receive email notifications when the workflow completes.  
- The workflow ensures that all code merged into the repository passes the test suite, thus increasing the reliability of the system.  

