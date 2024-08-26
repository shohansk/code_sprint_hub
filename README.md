<div align="center">
    <h1>Code Sprint Hub</h1>
    <h4>Django Rest Auth API</h4>
</div>

---


<div align="center">
    <img src="https://img.shields.io/badge/Python-3.10-green" />
    <img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json" />
</div>

---


---

## Indexes
- [Prerequisites](#prerequisites)
- [Project Setup](#project-setup)
- [Database Setup in Docker (Optional - Local)](#database-setup-in-docker-optional---local)
- [Create and Activate virtual environment](#create-and-activate-virtual-environment)
- [For Run Project](#for-run-project)


---

### Prerequisites
- Python >= 3.9
- PostgreSQL

### Project Setup:
```shell
1. git switch development
```
**Notes:**

***NB: Please convert the `env.example` to `.env` and put all necessary credentials*** 

##### Create and Activate virtual environment
```shell
1. python3 -m venv .venv
2. sourve .venv/bin/activate

```
##### For Run Project
```shell
1. pip install -r requirements.txt
2. mkdocs serve
```
**Notes:**

***NB: For Doc (http://127.0.0.1:8000/)*** 

##### For Deployment
```shell
mkdocs gh-deploy
```
