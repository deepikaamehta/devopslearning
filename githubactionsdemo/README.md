# GitHub Actions CI Demo (Python App)

This project demonstrates how to build a simple **Continuous Integration (CI) pipeline** using GitHub Actions for a Python application.

You'll learn how to:
- Run automated tests with `pytest`
- Lint your code with `flake8`
- Set up a CI pipeline that triggers on every push or pull request

---

## Project Structure

githubactionsdemo/
├── app/
│ └── calculator.py # Simple add function
├── tests/
│ └── test_calculator.py # Unit test for calculator
├── requirements.txt # Python dependencies
└── .github/
└── workflows/
└── ci.yml # GitHub Actions CI pipeline

yaml
Copy
Edit

---

## Getting Started Locally

### 1. Clone the repo

```bash
git clone https://github.com/deepikaamehta/devopslearning.git
cd devopslearning/githubactionsdemo
2. Create a virtual environment

python3 -m venv venv
source venv/bin/activate
3. Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
4. Run tests manually


pytest
🛠 GitHub Actions Workflow
The CI pipeline is defined in:
.github/workflows/ci.yml

Triggered on:
Push to main

Pull request to main

🔧 What it does:
Checks out code

Sets up Python environment

Installs dependencies

Lints code using flake8

Runs tests using pytest

 Sample Workflow Snippet:

name: Python CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt

      - name: Lint with flake8
        run: flake8 app/ tests/

      - name: Run unit tests
        run: pytest
What You'll See in GitHub
Once you push changes to main, GitHub will automatically:

Run flake8 to catch linting errors

Execute pytest to verify tests pass

Show build status in your PRs and commits

Author
Deepika Mehta
GitHub: @deepikaamehta
DevOps Journey — Days 18–20
Learning CI/CD with GitHub Actions

Next Steps (Optional Ideas)
Add code coverage reporting with pytest-cov

Auto-deploy using Docker or Heroku

Slack/email notification on failure

Deploy tagged versions only

