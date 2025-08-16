---
title: Deployment
has_children: false
nav_order: 8
---

# Deployment

This section explains what operations are needed to make the software work on the users' machine(s)

# User installation

Users need Python and optionally Docker if they want to run the software in a container.

- **What is it?**  
  1. Python 3.9+  
  2. pip (Python package installer)  
  3. Optional: Docker and Docker Compose

- **How to install it?**  

  **Python and pip:**
  ```bash
  # On Ubuntu/Debian
  sudo apt update
  sudo apt install python3 python3-pip

  # On MacOS (using Homebrew)
  brew install python3
  ```

Docker (optional, for containerized deployment)
# Install Docker
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
```

# Optionally install Docker Compose
```bash
sudo apt install docker-compose
```

## Instructions

# 1st Step: Clone the repository
```bash
git clone https://github.com/<org>/food-waste-manager.git
cd food-waste-manager
```

# 2nd Step: (Optional) Create a virtual environment and install dependencies:
```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```
# 3rd step: run the Streamlit app:
```bash
streamlit run app.py
```

# Server-side installation

The application uses SQLite for local storage. SQLite is included with Python by default, so no additional database installation is required. The database file will be created automatically when the application runs, making setup simple and straightforward.

If you prefer a containerized deployment, you can build and run the provided Docker image:
```bash
docker build -t ghcr.io/<org>/food-waste-manager:X.Y.Z .
docker run -d -p 8501:8501 ghcr.io/<org>/food-waste-manager:X.Y.Z
Once the app is running, it will be accessible through a browser at http://<server-ip>:8501/. No further server-side configuration is necessary, as SQLite handles data storage locally and the app is ready to run out of the box.
```