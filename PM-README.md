# ✅ AI Engineering Prompt for GitHub Actions: Project Manager's Complete Setup Guide

## 🤖 Prompt Objective

**As a technical business analyst turned program/project manager**, I want to build a foolproof technical workflow and folder structure that can be used to test and validate GitHub Actions for common developer tasks such as:

* ✅ CI/CD pipelines
* ✅ Markdown linting
* ✅ Python/R checks

This workflow must support any language or tech stack and simulate standard collaborative engineering practices.

The document must:

* Show how to set up project folders and files in Explorer
* Provide exact CMD/PowerShell/VSCode terminal commands
* Include all git and GitHub UI steps (branches, issues, PRs, and reviewers)
* Be Markdown-friendly and GitHub-ready
* Include `.gitignore` bonus steps

---

## 📁 Folder & File Structure (To Be Created Locally)

```plaintext
project-root/
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   └── project_overview.md
├── src/
│   └── placeholder.py  # or R script
├── tests/
│   └── test_placeholder.py
├── .gitignore
├── README.md
├── LICENSE
```

> 💡 Use File Explorer or VSCode Explorer to create each folder/file manually or use terminal commands below.

---

## 💻 Terminal Commands to Create Folders & Files

### CMD (Windows)

```bat
md project-root && cd project-root
md .github\workflows
md docs
md src
md tests
echo.>.gitignore
echo.>README.md
echo.>LICENSE
echo "print('Placeholder')" > src\placeholder.py
echo "def test_placeholder():\n    assert 1 == 1" > tests\test_placeholder.py
```

### PowerShell

```powershell
New-Item -Type Directory project-root | Set-Location
New-Item -Type Directory .github\workflows
New-Item -Type Directory docs, src, tests
New-Item -ItemType File -Name .gitignore, README.md, LICENSE
Add-Content -Path src\placeholder.py -Value "print('Placeholder')"
Add-Content -Path tests\test_placeholder.py -Value "def test_placeholder():`n    assert 1 == 1"
```

### VS Code Terminal (Bash Style)

```bash
mkdir -p project-root/.github/workflows && cd project-root
mkdir docs src tests
touch .gitignore README.md LICENSE
echo "print('Placeholder')" > src/placeholder.py
echo "def test_placeholder():\n    assert 1 == 1" > tests/test_placeholder.py
```

---

## 🧪 Sample GitHub Actions Workflow: `.github/workflows/ci.yml`

```yaml
name: CI Pipeline
on:
  push:
    branches: [ main, dev ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repo
        uses: actions/checkout@v4

      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.x'

      - name: Install Linting Tools
        run: pip install flake8 markdownlint-cli

      - name: Lint Python Code
        run: flake8 src/

      - name: Lint Markdown Docs
        run: markdownlint docs/
```

---

## 🚀 Git Commands and GitHub Workflow

### 🔧 Git Initialization & Commit

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

### 🌿 Create Dev Branch

```bash
git checkout -b dev
git push -u origin dev
```

---

## 📌 GitHub Web UI Instructions

1. **Create an Issue:**

   * Go to Issues → New Issue
   * Title: "Test GitHub Actions Trigger"
   * Assign to yourself and label as `automation`

2. **Create Pull Request:**

   * Dev → Main
   * Include the issue in the PR body using `Closes #1`
   * Add reviewer (you or a teammate)
   * Enable required review before merge (Settings → Branches → Rules)

3. **Watch Actions Run**

   * Navigate to **Actions** tab in your repo after PR is created
   * Observe CI pipeline results

---

## 📁 .gitignore Sample (Python/R focused)

```gitignore
# Python
__pycache__/
*.pyc
.env

# R
.Rhistory
.RData
.Rproj.user/

# General
.DS_Store
.vscode/
.idea/
```

---

## 🧠 Final Note

This modular setup is designed for **PMs and BAs** to collaborate with developers and DevOps teams by simulating GitHub Actions workflows for CI/CD, markdown linting, and code checks. Feel confident in managing repo automation from a strategic and technical perspective.

You can now extend this with test runners, container builds, or AI-enhanced checks!
