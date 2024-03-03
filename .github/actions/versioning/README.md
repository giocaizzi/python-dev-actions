# Versioning

Handle versioning.

Checks if the package version has been updated in **setup.py** and **__init_.py**

Inputs:
- `packaging-style` : The python packaging style used in the repository (`setup.py` or `pyproject.toml`). Default `setup.py`.
- `package-folder` : The folder where the package is located. Default `` aka root.



> **Note**
>
> It requires a runner where the repository is checked out with `fetch-depth:0`, so to to allow merging.
