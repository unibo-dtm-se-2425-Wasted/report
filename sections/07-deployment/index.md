---
title: Deployment
has_children: false
nav_order: 8
---

# Deployment

The **“Wasted”** application can be run both locally and directly online via Streamlit Cloud.

# 1. Local Execution


Users need Python and optionally Docker if they want to run the software in a container.

- **What is it?**  
  1. Python 3.9+  
  2. pip (Python package installer)  

- **How to install it?**  

  **Python and pip:**
  ```bash
  # On Ubuntu/Debian
  sudo apt update
  sudo apt install python3 python3-pip

  # On MacOS (using Homebrew)
  brew install python3
  ```


## Instructions

**1st Step: clone the repository**
```bash
git clone https://github.com/<org>/food-waste-manager.git
cd food-waste-manager
```

**2nd step: run the Streamlit app**
```bash
streamlit run app.py
```

# Server-side installation

The application uses SQLite for local storage. SQLite is included with Python by default, so no additional database installation is required. The database file will be created automatically when the application runs, making setup simple and straightforward.

# 2.  Online Deployment (Streamlit Cloud)

The app has been published on **Streamlit Cloud**, which allows it to be run directly without any local installation.  
The official link to access the app is:

[https://wastedapp.streamlit.app//](https://wastedapp.streamlit.app//)

This link always points to the latest version of the app based on the most recent commits to the main branch of the repository.