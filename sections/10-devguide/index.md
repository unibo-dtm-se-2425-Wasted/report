---
title: Developer guide
has_children: false
nav_order: 11
---

## Developer Guide

This section provides guidance for new developers joining the **Wasted** project. It explains how to set up the environment, follow internal conventions, and contribute effectively.

### 1. Team & Communication

* **Contact**: The development team can be reached via the shared project email or the university course repository.
* **Issue Reporting**: Bugs, feature requests, and questions should be reported in the project’s GitHub Issues page. Always include steps to reproduce and screenshots if applicable.

### 2. Conventions & Coding Style

* **Language**: Python 3.11 with Streamlit for the web interface, SQLite for the database.
* **Naming Conventions**:
  * Variables and functions → mostly `snake_case`, with occasional `camelCase` in Streamlit session state or UI components.
  * Classes → `PascalCase` (rarely used, since the project is mostly function-based).
  * Constants → not consistently formalized, but written in uppercase when present.
* **Comments**: Comments are added for non-trivial logic, while function names are generally chosen to be self-explanatory. Docstrings are used in some functions, but not systematically across the project.
* **Code Formatting**: Formatting is applied manually with a focus on readability and consistency, though some minor inconsistencies may remain.


### 3. Development Environment

3.1. **Clone the Repository**

   ```bash
   git clone https://github.com/<project-repo>.git
   cd food-waste-manager
   ```
3.2. **Set Up Virtual Environment**

   ```bash
   python -m venv venv
   source venv/bin/activate   # (Mac/Linux)
   venv\Scripts\activate      # (Windows)
   ```
3.3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```
3.4. **Run the App**

   ```bash
   streamlit run app.py
   ```
3.5. **Database**

   * The project uses **SQLite**, with the database file located in `/data/food_items.db`.
   * The schema initializes automatically if the file does not exist.

### 4. Workflow

* **Branching Model**:

* `main` → stable production branch.  
* Individual development branches → each team member has their own development branch, e.g., `Mai`, `Sara`, `Viola`.  
* Feature work → create a new branch from your personal development branch, typically named after the feature, e.g., `feature/feature-name`.


    ```bash
    git checkout -b feature/<feature-name>
    ```

* **Commits**: Follow clear messages in the form:

  ```
  [type]: short description
  ```

  Examples:

  * `feat: add logout button`
  * `fix: handle null expiration dates`
  * `docs: update developer guide`

* **Pull Requests (PRs)**:

  * Create PRs into development branches.
  * At least one reviewer must approve before merging.
  * Use draft PRs for work-in-progress features.

### 5.Tools & IDE

* **IDE**: Recommended → **VS Code** with Python, GitLens, and Black extensions.
* **Version Control**: GitHub is the central repository.
* **Command Line**: Developers should be comfortable running Git commands, activating the virtual environment, and starting the Streamlit server.




