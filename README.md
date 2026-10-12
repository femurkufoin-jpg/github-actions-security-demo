GitHub Actions Security Demo
1. Project Overview
This project demonstrates how to automate testing, code quality checks, and security checks for a Python application using GitHub Actions.
The workflow runs automatically when code is pushed to main or a feature/** branch, and when a pull request targets main.
2. Technologies Used
Python
pytest — automated testing
Flake8 — code quality and style checks
Bandit — Python security scanning
pip-audit — dependency vulnerability auditing
Git and GitHub
GitHub Actions — workflow automation
3. Project Structure
github-actions-security-demo/
├── .github/
│   └── workflows/
│       └── security-checks.yml
├── app/
│   └── app.py
├── tests/
│   └── test_app.py
├── .gitignore
├── requirements.txt
├── requirements-dev.txt
└── README.md
4. Prerequisites
Install the following before running the project locally:
Python 3
Git
pip, the Python package installer
5. Run the Project Locally
Open a terminal in the repository directory.
Create and activate a virtual environment on Windows PowerShell:
python -m venv .venv
.\.venv\Scripts\Activate.ps1
Install the project dependencies and development tools:
python -m pip install -r requirements.txt
python -m pip install -r requirements-dev.txt
Run the automated tests:
python -m pytest -v
Run the code quality check:
python -m flake8 app tests
Scan the Python application for security issues:
python -m bandit -r app
Audit the installed application dependencies:
python -m pip_audit -r requirements-dev.txt
6. GitHub Actions Security Workflow
The workflow is defined in .github/workflows/security-checks.yml.
It performs the following steps:
Checks out the repository code.
Sets up Python.
Installs the required development tools.
Runs automated tests with pytest.
Checks code quality with Flake8.
Scans Python code with Bandit.
Audits dependencies with pip-audit.
The workflow runs automatically on the configured push and pull request events. Results can be viewed in the repository’s Actions tab.
7. Troubleshooting
Python tools are not recognized
Install the development dependencies and invoke the tools through Python:
python -m pip install -r requirements-dev.txt
python -m flake8 app tests
Tests fail
Run the tests locally to inspect the error:
python -m pytest -v
Check the failing test and the corresponding application code before pushing again.
GitHub Actions workflow does not run
Verify that the workflow file is located at:
.github/workflows/security-checks.yml
Check that the workflow triggers match the branch and event being used. Open the Actions tab to inspect failed runs and their logs.
Security tools report findings
Review the findings and investigate whether they represent actual issues. Fix confirmed problems and rerun the relevant checks. Do not automatically ignore findings without understanding them.
8. Git Workflow
The project uses feature branches and pull requests to introduce changes safely.
git switch -c feature/your-change
git add .
git commit -m "docs: update project documentation"
git push -u origin feature/your-change
Open a pull request on GitHub, verify the workflow checks, and merge into main when ready.
9. Project Evidence
Evidence for this project includes:
The security workflow configuration.
Successful GitHub Actions runs.
The pull request and successful merge into main.
Local test and security-check results.
10. Conclusion
This project demonstrates a basic DevSecOps workflow by integrating automated testing, code quality checks, Python security scanning, and dependency auditing into GitHub Actions. It also demonstrates the use of feature branches, commits, pull requests, and automated checks before merging changes into the main branch.