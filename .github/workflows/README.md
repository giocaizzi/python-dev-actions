# Workflows

Reusable workflows.

- [deployment.yml](#deployment): Test and deploy the python package for a given `os`.
- [documentation.yml](#documentation): Build Sphinx documentation on python 3.9. 

## Deployment

[deployment.yml](./deployment.yml) deploys the python package on specific `os` with a specific `python-version`.

Testing is done on on a matrix of multiple python versions `python-tested-versions` that is passed as a stringfied list of strings. Defaults range is `>=3.7,<=3.12`.

```yml
    python-tested-versions: "['3.7', '3.8', '3.9', '3.10','3.11','3.12']"
```

Inputs:
- `os`: operating system. Defaults to `ubuntu-latest`.
- `python-version` : python version, Defaults to `3.9`.
- `python-tested-versions`: stringfied list of string versions. Defaults to `['3.7', '3.8', '3.9', '3.10','3.11','3.12']`

The deployment is made of two jobs:
- `pre-checks`: execute pre-checks with `python-version` on `os`.
    - [Linting](../actions/lint/README.md)
    - [Versioning](../actions/versioning/README.md)
    - [Documentation merge check](../actions/documentation-merge-check/README.md)

- `tests`: test on `python-tested-versions` with `os`.
    - [tests](../actions/tests/README.md)

## Documentation

[documentation.yml](./documentation.yml) builds the docs using sphinx on python 3.9

*This workflow is optimized for a **ghpages** separate branch structure.

