---
title: CI/CD
has_children: false
nav_order: 9
---

# CI/CD

## Conceptual description

The project exploits a **Continuous Integration / Continuous Delivery (CI/CD)** workflow based on **GitHub Actions**.  
The purpose of the workflow is to ensure that the system remains stable and correct at every commit, by automatically executing the defined test suite.  

### What is automated?
- **Continuous Integration (CI):**  
  - Every push and pull request on the main branch automatically triggers the workflow.  
  - The workflow installs dependencies and runs all unit tests.  
  - If tests fail, the workflow is marked as failed and contributors are notified by email.  

- **Continuous Delivery (CD):**  
  - At this stage, no deployment automation is implemented.  
  - However, the project is structured so that adding a deployment step (e.g., building a Docker image or deploying to a hosting service) would be straightforward.

### Why?
- To guarantee that new changes do not break existing functionality.  
- To enforce code quality by requiring that all tests pass before merging.  
- To provide immediate feedback to developers through GitHub’s email notifications and status checks.  

### How?
- GitHub Actions uses a YAML configuration file (placed in `.github/workflows/`) that specifies:  
  - The **trigger** (push, pull request).  
  - The **environment** (Python version).  
  - The **jobs** (install dependencies, run tests).  
- Tests are executed in a clean virtual environment provided by GitHub runners (Ubuntu-based).  

## GitHub Actions implementation details

- **Runner environment:** GitHub-hosted runner with Ubuntu and Python preinstalled.  
- **Dependencies:** Installed via `pip`, based on the `requirements.txt` file.  
- **Test execution:** Uses the standard `unittest` test discovery (`python -m unittest discover`).  
- **Secrets / environment variables:**  
  - No external secrets or tokens were needed for the current project.  
  - If future deployment is added (e.g., to Docker Hub or a cloud service), GitHub Actions secrets would be required to securely store credentials.  

## Current status

- The CI workflow is active and working: contributors receive email notifications when the workflow completes.  
- The workflow ensures that all code merged into the repository passes the test suite, thus increasing the reliability of the system.  

