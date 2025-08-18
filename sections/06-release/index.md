---
title: Release
has_children: false
nav_order: 7
---

# Release

From the project’s codebase, the following artefacts are generated:

1. **Python package**
   - `food_waste_manager-X.Y.Z.tar.gz` → **Source Distribution (sdist)** containing raw source code and metadata.
   - `food_waste_manager-X.Y.Z-py3-none-any.whl` → **Wheel (binary distribution)**, pre-built for faster installation.
   - Both artefacts include the Streamlit app and Python modules (`app.py`, `db/database.py`, tests).

2. **Docker image** (`ghcr.io/<org>/food-waste-manager:X.Y.Z`)
   - Contains the Streamlit app fully packaged and ready to run in a container.
   - Suitable for deployment to servers, cloud environments, or orchestration platforms (e.g., Kubernetes).

# Publishing repositories
- **PyPI** (public or private) for the Python package.  
  *Reason:* Easy installation via `pip`.

- **Docker Hub** or **GitHub Container Registry (GHCR)** for the Docker image.  
  *Reason:* Rapid deployment without local Python configuration.

# Release process
Releases are automated with **GitHub Actions**.

# General configuration
1. Create `.github/workflows/release.yml`.
2. Trigger the workflow on **tag push** (`vX.Y.Z`) in GitHub.
3. Workflow steps:
   - Run tests (`pytest` / `unittest`).
   - Build Python package (`python -m build`).
   - Publish to PyPI with `twine upload dist/*`.
   - Build Docker image (`docker build`).
   - Push Docker image to Docker Hub or GHCR (`docker push`).

# Manual release commands
```bash
# 1. Update version in pyproject.toml or setup.py
# 2. Build Python package
python -m build

# 3. Publish to PyPI
twine upload dist/*

# 4. Build and push Docker image
docker build -t ghcr.io/<org>/food-waste-manager:X.Y.Z .
docker push ghcr.io/<org>/food-waste-manager:X.Y.Z
```

# Choice of the license
# Code license
We have chosen the **MIT License** for the project’s source code.

**Reasons:**
- **Simplicity:** The MIT License is short, clear, and easy to understand for both developers and legal teams.
- **Permissiveness:** It allows anyone to use, modify, distribute, and sublicense the code with minimal restrictions.
- **Widespread adoption:** It is one of the most popular open-source licenses, which improves trust and compatibility with other projects.
- **Encourages contributions:** Developers are more likely to contribute when licensing terms are non-restrictive.

---

# Artefacts license
The produced artefacts (Python package and Docker image) are also released under the **MIT License**.

**Reasons:**
- **Consistency:** Using the same license as the source code ensures there is no legal conflict between code and distributed artefacts.
- **Uniform legal terms:** Users and integrators know exactly what rights and obligations they have, regardless of whether they use the code directly or the pre-built artefacts.
- **Ease of redistribution:** The MIT License allows the artefacts to be redistributed without complex legal processes.

# Choice of the versioning schema

We use **Semantic Versioning (SemVer)**: `MAJOR.MINOR.PATCH`

- **MAJOR** → Breaking API changes or major refactors.  
- **MINOR** → Backward-compatible new features.  
- **PATCH** → Bug fixes and small improvements.  

---

# Multiple artefacts

All artefacts share the same version number:

- Ensures traceability.  
- Guarantees the Docker image corresponds exactly to the same code as the Python package.  

---

# Creating a new version

1. **Update the version** in `pyproject.toml` or `setup.py`.

2. **Commit changes** and create a branch:

```bash
release/X.Y.Z
Tag the release:

bash
git tag vX.Y.Z
git push origin vX.Y.Z

GitHub Actions will automatically:
-Build and publish the Python package to PyPI.
-Build and push the Docker image to Docker Hub / GHCR.
-Create a GitHub Release linked to the tag and add release notes.
```
