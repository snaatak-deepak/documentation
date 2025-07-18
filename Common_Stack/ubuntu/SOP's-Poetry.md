# Poetry Standard Operating Procedure (SOP)

## Metadata


| **Author**        | **Created on** | **Version** | **Last Updated** |
|-------------------|----------------|-------------|------------------|
| Deepak Kushwaha   | 18-07-2025     | v1.0        | 18-07-2025       |

---

## Table of Contents

- [ Introduction](#introduction)
- [ Prerequisites](#️prerequisites)
- [ Creating a New Project](#creating-a-new-project)
- [ Managing Virtual Environments](#managing-virtual-environments)
- [ Adding & Managing Dependencies](#adding--managing-dependencies)
- [ Running Commands in Poetry Context](#running-commands-in-poetry-context)
- [ Additional Tips](#additional-tips)
- [ Reference Links](#reference-links)

---

## Introduction

**Poetry** is a modern Python tool for managing dependencies and packaging. It replaces `pip`, `requirements.txt`, and `venv` by combining them into one robust, developer-friendly workflow.

---

## 1. Prerequisites

- Python ≥ 3.7 installed
- Poetry installed using:

  ```bash
  curl -sSL https://install.python-poetry.org | python3
  ```

- Ensure poetry is available in your shell's PATH:

   ```bash
   poetry --version
   ```

## 2. Creating a New Project

- Create a new structured Python project:

  ```bash
  poetry new myproject
  cd myproject
  ```

- This creates:
  ```bash
  myproject/
  ├── pyproject.toml
  ├── README.rst
  └── myproject/
      └── __init__.py
  ```

## 3. Managing Virtual Environments

#### Poetry automatically manages isolated virtual environments per project.

- Activate shell:
  ```bash
  poetry shell
  ```

- Exit Poetry shell:
  ``` bash
  exit
  ```

- Show venv path:
  ```bash
  poetry env info --path
  ```

- Remove virtual environment:
  ```bash
  poetry env remove python
  ```

## 4. Adding the Managing Dependencies

- Add a runtime dependency:
  ```bash
  poetry add requests
  ```

- Add a dev dependency (for testing/linting):
  ``` bash
  poetry add --dev pytest
  ```

- Install all dependencies from pyproject.toml:
  ```bash
  poetry install
  ```

- Update dependencies to latest allowed versions:
  ```bash
  poetry update
  ```

## 5. Running Commands in Poetry Context

#### Use poetry run to run commands inside the virtual environment without manually activating it:

- Run Python script:
  ```bash
  poetry run python script.py
  ```

- Run pytest:
  ```bash
  poetry run pytest
  ```

---

## Contact Information

| **Name**           | **Email address**                         |
|--------------------|--------------------------------------------|
| Deepak Kushwaha    | [deepak.kushwaha.snaatak@mygurukulam.co](mailto:deepak.kushwaha.snaatak@mygurukulam.co) |

---

## References Links

| **Link**                                                                 | **Description**                                   |
|--------------------------------------------------------------------------|---------------------------------------------------|
| [ Official Documentation ](https://python-poetry.org/docs/) | Document format followed from this link.          |




## Author

- [Deepak Kushwaha](#)








