---
title: Developer guide
has_children: false
nav_order: 11
---

# Developer Guide

This section explains how can a new person enter the development team and start contributing to the project.
- report any relevant organizational information (e.g. how to contact the team, how to report issues, etc.)
- report any internal convention that the team follows (e.g. naming conventions, coding style, etc.)
- report any relevant information about the development environment (e.g. how to set it up, how to run the tests, etc.)
- report any relevant information about the development workflow (e.g. how to create a new feature branch, how to create a pull request, etc.)
- report any relevant information about the development tools (e.g. how to configure the IDE, how to use the command line, etc.)

Perfect 👍 For your **Developer Guide** section, here’s a structured draft you can insert into the report. It’s professional but also simple enough for a student project.

---

## Developer Guide

This section provides guidance for new developers joining the **Food Waste Manager** project. It explains how to set up the environment, follow internal conventions, and contribute effectively.

### 1. Team & Communication

* **Contact**: The development team can be reached via the shared project email or the university course repository.
* **Issue Reporting**: Bugs, feature requests, and questions should be reported in the project’s GitHub Issues page. Always include steps to reproduce and screenshots if applicable.

### 2. Conventions & Coding Style

* **Language**: Python 3.11 with Streamlit for the web interface, SQLite for the database.
* **Naming Conventions**:

  * Variables and functions → `snake_case`
  * Classes → `PascalCase`
  * Constants → `ALL_CAPS`
* **Comments**: Use inline comments for tricky logic and docstrings for functions.
* **Code Formatting**: We recommend using **Black** (autoformatter) and **flake8** (linting).

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
  * `dev` → development branch.
  * Feature work → create a new branch:

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

  * Create PRs into `dev`.
  * At least one reviewer must approve before merging.
  * Use draft PRs for work-in-progress features.

### 5.Tools & IDE

* **IDE**: Recommended → **VS Code** with Python, GitLens, and Black extensions.
* **Version Control**: GitHub is the central repository.
* **Command Line**: Developers should be comfortable running Git commands, activating the virtual environment, and starting the Streamlit server.
* **Optional Tools**:

  * **SQLite Browser** for inspecting the database.
  * **Postman/Insomnia** if API testing is needed.


