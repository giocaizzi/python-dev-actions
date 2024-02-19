# Workflows

Reusable workflows.

## Complex workflows

Complex workflows perform a set of tasks calling underlying base workflows.

### deployment.yml

[Deploy](./deployment.yml) the python package for a given `os` and testing it on a matrix of `python-version`s.

## Base workflows

These are minimal workflows performing a specific task.

### pre-checks.yml

[Pre-checks](./pre-checks.yml): Preliminary checks to code.
- Linting with flake8
- Versioning checks

*Args*:
 - `python-version` : python version to use. Defaults to `3.9`
 - `os`: os to use. Defaults to `ubuntu-latest`

### tests.yml

[Tests](./tests.yml): Run tests on a matrix of Python version

*Args*:
- `os`: os to use. Defaults to `ubuntu-latest`