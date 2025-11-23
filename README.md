GitHub Actions Linting Demo
https://github.com/csagdpodpadma/gitadminrepo/actions/workflows/main.yml/badge.svg

📌 Overview
This repository demonstrates how to use GitHub Actions to run Super-Linter for automated code quality checks.
It’s designed for workshops and training sessions to showcase CI/CD best practices.

✅ Features

GitHub Actions workflow using Super-Linter.
Runs on push and pull requests to the main branch.
Provides real-time linting feedback in the Actions tab.


📂 Repository Structure
.gitHub/workflows/main.yml   # GitHub Actions workflow
src/sample.py                # Sample Python file with lint issues
README.md                    # Project documentation


🔑 Prerequisites

GitHub account
Basic knowledge of Git and GitHub Actions
A repository with Actions enabled


🚀 How to Run

Clone the repository
Shellgit clone https://github.com/csagdpodpadma/gitadminrepo.gitcd gitadminrepoShow more lines

Make a change and push
Shellecho "# New line" >> src/sample.pygit add .git commit -m "Trigger workflow"git push origin mainShow more lines

Check the Actions tab

Navigate to Actions in your GitHub repo.
Select Lint Code Base workflow.
View logs for success or failure.




🛠 Workflow Details
The workflow uses https://github.com/github/super-linter to validate code quality.
Here’s the core configuration in .github/workflows/main.yml:
YAMLname: Lint Code Baseon:  push:    branches: [main]  pull_request:    branches: [main]jobs:  lint:    runs-on: ubuntu-latest    steps:      - name: Checkout Code        uses: actions/checkout@v4        with:          fetch-depth: 0      - name: Lint Code Base        uses: github/super-linter@v5        env:          VALIDATE_ALL_CODEBASE: true          DEFAULT_BRANCH: mainShow more lines

🎯 Workshop Demo Script

Push the workflow file:
Shellgit add .git commit -m "Add GitHub Actions workflow"git push origin mainShow more lines

Show Actions tab → Workflow run.
Fix lint error in src/sample.py:
Shellecho "" >> src/sample.pygit add src/sample.pygit commit -m "Fix lint issue"git push origin mainShow more lines

Show successful run.


📈 Bonus

Add a status badge in README (already included).
Explain benefits of CI/CD automation.
Optional: Extend workflow with caching and matrix builds.

