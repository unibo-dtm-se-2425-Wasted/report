
# Developer Guide 

This guide helps new developers join the **WASTED** project, set up their environment, and start contributing effectively.


## 1. Team & Communication

* **Repository**: Hosted on GitHub under the team account.
* **Contact**: Communication is managed through GitHub Issues & Discussions.
* **Reporting Issues**:

  * Open an Issue on GitHub.
  * Use clear labels: `bug`, `feature`, `documentation`.
  * Include screenshots, logs, or reproduction steps when possible.


## 2. Project Overview

* **Frontend**: Built with **Streamlit** (Python web framework).
* **Database**: Uses **SQLite** (`data/food_items.db`) – automatically created if missing.
* **Features**:

  * Add, edit, delete food items.
  * Track expiration dates and status (Expired / Expiring Soon / Fresh).
  * User authentication (basic login/logout).
  * Recipe suggestions via external API (images may sometimes mismatch recipes).


## 3. Conventions

* **Naming**:

  * Files → `snake_case.py`
  * Variables & functions → `snake_case`
  * Classes → `PascalCase`
* **Style**:

  * Follow [PEP 8](https://peps.python.org/pep-0008/).
  * Use meaningful commit messages:

    * `feat: add logout button`
    * `fix: handle null expiration dates`
    * `docs: update developer guide`
* **Branches**:

  * `main` → stable release branch
  * Individual development branches → each team member has their own development branch, e.g., `Sara`, `Viola`, `Mai`.  
  * `yourname` → for new features


## 4. Development Environment

### Setup Steps

```bash
# 1. Clone the repo
git clone https://github.com/unibo-dtm-se-2425-Wasted/report.git
cd wasted

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the app
streamlit run app.py
```

* The **SQLite database** is located in `data/food_items.db`.
* It initializes automatically on first run.


## 5. Development Workflow

1. Create a feature branch:

   ```bash
   git checkout -b `yourname`
   ```
2. Implement your changes.
3. Test locally:

   ```bash
   streamlit run app.py
   ```
4. Commit with meaningful messages.
5. Push branch and create a Pull Request into `yourname`.
6. Once reviewed, it will be merged into `main`.


## 6. Tools & Recommendations

* **IDE**: Visual Studio Code with Python, Black, and GitLens extensions.
* **Database Tool**: DB Browser for SQLite (optional for inspecting DB).
* **Version Control**: GitHub (all code and releases are maintained here).
* **APIs**: Recipe API (external dependency). Handle mismatched images gracefully.


