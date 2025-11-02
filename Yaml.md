# AI-Powered Playwright Test Executor — Setup Guide

This document explains how to configure and run an **AI-driven Playwright test executor** using Node.js and a GitHub Actions workflow.


## Overview

This setup allows you to:
- Install Playwright and AI SDKs (OpenAI + Anthropic)
- Automatically create a JavaScript test runner (`ai-test-executor.js`)
- Parse and execute test cases written in **Markdown (`Testsuite.md`)**
- Automate real web actions using **Playwright**


## Prerequisites

Before running this workflow, ensure the following are installed or configured:
- Node.js v18+  
- npm (comes with Node.js)
- GitHub Actions runner or local terminal environment  
- A valid `Testsuite.md` file containing test cases

## Step 1: Prepare Your Project

1. Create a new folder for your automation project:
   ```bash
   mkdir ai-test-runner
   cd ai-test-runner
   ```

2. Initialize npm:
   ```bash
   npm init -y
   ```

3. Create an empty Markdown test suite file:
   ```bash
   echo "## TC 001 - Register new user" > Testsuite.md
   ```

   Example content for `Testsuite.md`:
   ```markdown
   ## TC 001 - Register new user
   - Navigate to `https://parabank.parasoft.com`
   - Click on the Register link
   - Fill the registration page
   - Submit the form
   - Verify that welcome message is displayed
   ```

---

## Step 2: Add the GitHub Actions Workflow

Create a workflow file in your repository:  
**`.github/workflows/ai-test-executor.yml`**

```yaml
name: AI Test Executor

on:
  workflow_dispatch:

jobs:
  run-ai-tests:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Install Playwright
        run: |
          npm init -y
          npm install playwright @playwright/test
          npx playwright install

      - name: Install AI Test Runner
        run: |
          npm install openai
          npm install @anthropic-ai/sdk

      - name: Create AI Test Executor
        run: |
          cat > ai-test-executor.js << 'EOF'
          [JavaScript code content goes here — your ai-test-executor.js logic]
          EOF

      - name: Run AI Test Executor
        run: |
          node ai-test-executor.js
```

---

## Step 3: How It Works

| Step | Description |
|------|--------------|
| **Install Playwright** | Installs browser automation framework and its dependencies. |
| **Install AI Test Runner** | Installs OpenAI and Anthropic SDKs to enable AI-driven logic. |
| **Create AI Test Executor** | Dynamically creates a JS file that reads `Testsuite.md`, parses each test case, and runs them in a headless Chromium browser. |
| **Run AI Test Executor** | Executes all test cases and prints results in the workflow logs. |

---

## Step 4: Running Tests Locally (Optional)

You can also run the same test locally:
```bash
node ai-test-executor.js
```

This will:
1. Launch a **headless Chromium browser**.
2. Execute test steps from your `Testsuite.md`.
3. Output each test’s status (`PASS` / `FAIL`) in the console.

## Optional Enhancements

You can extend this setup by:
- Adding **AI-generated test case creation** using the OpenAI SDK.
- Generating **HTML or JSON reports** automatically.
- Integrating with **CI/CD pipelines** (Jenkins, Azure DevOps, GitLab CI, etc.).
