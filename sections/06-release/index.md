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

# Publishing repository
- **PyPI** (public or private) for the Python package.  
  *Reason:* Easy installation via `pip`.

# Release process
Releases are automated with **GitHub Actions**.

# General configuration
1. Create `.github/workflows/release.yml`.
2. Trigger the workflow on **tag push** (`vX.Y.Z`) in GitHub.
3. Workflow steps:
   - Run tests (`pytest` / `unittest`).
   - Build Python package (`python -m build`).
   - Publish to PyPI with `twine upload dist/*`.


# Manual release commands
```bash
# 1. Update version in pyproject.toml or setup.py
# 2. Build Python package
python -m build

# 3. Publish to PyPI
twine upload dist/*

```




# Choice of the versioning schema

We use **Semantic Versioning (SemVer)**: `MAJOR.MINOR.PATCH`

- **MAJOR** → Breaking API changes or major refactors.  
- **MINOR** → Backward-compatible new features.  
- **PATCH** → Bug fixes and small improvements.  

---

# Multiple artefacts

All artefacts share the same version number:
- Ensures traceability.
- Guarantees the package corresponds exactly to the same code as the Python package. 

---

# Creating a new version

1. **Update the version** in `pyproject.toml` or `setup.py`.

2. **Commit changes** and create a branch:

```bash
git checkout -b release/X.Y.Z
git commit -am "Release X.Y.Z"
```
3. **Tag the release:**
```bash
git tag vX.Y.Z
git push origin vX.Y.Z

GitHub Actions will automatically:
Build and publish the Python package to PyPI.
Create a GitHub Release linked to the tag and add release notes.
```
