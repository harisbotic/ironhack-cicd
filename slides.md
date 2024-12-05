# Slides: Basic CI/CD Pipeline with GitHub Actions

---

## Slide 1: Title Slide
---
**Basic CI/CD Pipeline with GitHub Actions**  
*Module 5: Advanced Java, Software Testing/QA & DevOps*  
Presented by: Haris Botić

---

## Slide 2: Agenda
---
1. Ice Breaker: The Importance of Naming
2. Software Development Lifecycle & CI/CD
3. What is CI/CD?
4. Introduction to GitHub Actions
5. GitHub Actions Workflow Example
6. Check for Understanding (CFU)
7. Setting Up GitHub Actions
8. Creating a Basic Workflow
9. Adding Deployment to the Pipeline
10. Check for Understanding (CFU)
11. Lab Introduction

---

## Slide 3: The Importance of Naming
---

**Inspiring Quotes:**

> "The naming of a thing is the first step in understanding it."  
> — J.R.R. Tolkien, "On the Origin of Names"

> "The ability to name and categorize is the foundation of scientific understanding."  
> — David Deutsch, "The Beginning of Infinity"

---

## Slide 4: Software Development Lifecycle & CI/CD
---
**Traditional Development Cycle:**
- Less frequent releases
- Manual testing phases
- High risk deployments

**Life Without CI/CD:**
- Time-consuming manual builds
- Integration conflicts discovered late
- Deployment anxiety
- Difficult rollbacks
- Delayed customer feedback

**Where CI/CD Fits:**
- Automates repetitive tasks
- Catches issues early in development
- Enables rapid, confident releases
- Provides immediate feedback
- Supports agile development practices

---

## Slide 5: What is CI/CD?
---
**Continuous Integration (CI):**
- Merging code changes frequently
- Automated testing to detect issues early

**Continuous Deployment (CD):**
- Automatically deploying code to production
- Ensures rapid release cycles

**Importance:**
- Enhances software quality
- Accelerates development process
- Reduces manual errors

---

## Slide 6: Introduction to GitHub Actions
---
- **What are GitHub Actions?**
  - CI/CD platform integrated with GitHub
  - Automate build, test, and deployment pipelines

- **Key Components:**
  - **Workflows:** Automated processes
  - **Jobs:** Set of steps executed on the same runner
  - **Steps:** Individual tasks within jobs
  - **Actions:** Reusable extensions for workflows

---

## Slide 7: GitHub Actions Workflow Example
---

```yaml
name: CI Pipeline
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Set up JDK 11
        uses: actions/setup-java@v1
        with:
          java-version: '11'
      - name: Build with Maven
        run: mvn clean install
```

---

## Slide 8: Quick Quiz - Check For Understanding (CFU)
---
**Activity Type:** Quick Quiz (Pairs)
**Duration:** 3 minutes discussion + 2 minutes review
**Objective:** Validate understanding of CI/CD fundamentals through interactive questions

**Activity content at [activity-1.md](activity-1.md)**

---

## Slide 9: Setting Up GitHub Actions
---
**Steps:** *Teacher will demo the steps below*

1. **Navigate to Actions Tab:**
   - Click on the "Actions" tab in your GitHub repository.

2. **Choose a Starter Workflow:**
   - Select a template based on your project's language or framework.

3. **Understand Workflow YAML:**
   - Define triggers, jobs, and steps in the `.github/workflows/` directory.

---

## Slide 10: Creating a Basic Workflow
---
**Steps:** *Teacher will demo the steps below*

1. **Create Workflow File:**
   - Path: `.github/workflows/ci.yml`

2. **Define Triggers:**
   - Example: On push to `main` branch or on pull requests.

3. **Add Jobs and Steps:**
   - Example jobs: Checkout code, set up environment, run tests.

4. **Run and Monitor:**
   - Commit changes and observe the workflow in the Actions tab.

---

## Slide 11: Adding Deployment to the Pipeline
---
**Steps:** *Teacher will demo the steps below*

1. **Choose Deployment Target:**
   - GitHub Pages, AWS, Heroku, etc.

2. **Configure Deployment Credentials:**
   - Store secrets in GitHub for secure access.

3. **Add Deployment Step in Workflow:**
   - Use deployment actions or scripts to automate the process.

**Example: Deploy to GitHub Pages**

```yaml
name: Deploy to GitHub Pages
uses: peaceiris/actions-gh-pages@v3
with:
  github_token: ${{ secrets.GITHUB_TOKEN }}
  publish_dir: ./public
```

---

## Slide 12: Check for Understanding (CFU)
---
**Activity Type:** Quick Quiz (Pairs)
**Duration:** 15 minutes
**Objective:** Reinforce key concepts of CI/CD and GitHub Actions through interactive questions.


**Activity content at [activity-2.md](activity-2.md)**
---

## Slide 13: Lab Introduction
---
**Lab Objectives:**

- Set up a GitHub Actions workflow in a sample repository.
- Automate the build and test process using GitHub Actions.
- Extend the workflow to include a deployment step.

**Duration:** 1-2 Hours

**Instructions:**
1. Access the lab repository.
2. Follow the lab guide to implement the CI/CD pipeline.
3. Submit your workflow file and deployment confirmation.

---

## Slide 14: Additional Resources
---
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [CI/CD Best Practices](https://www.redhat.com/en/topics/devops/what-is-ci-cd)
- [GitHub Actions Starter Workflows](https://github.com/actions/starter-workflows)
- [Continuous Integration vs Continuous Deployment](https://www.atlassian.com/continuous-delivery/ci-vs-ci-cd)

---

## Slide 15: Q&A and Wrap-Up
---
- Open floor for questions.
- Recap key takeaways.

---

# Thank You!
---
*Happy Coding!*