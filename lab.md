# Lab: Creating a Basic CI/CD Pipeline with GitHub Actions

## Introduction
In this lab, you will apply the concepts learned in the lesson to create and configure a CI/CD pipeline using GitHub Actions. You will automate the build and testing process and extend the pipeline to include a deployment step.

## Objectives
- Set up GitHub Actions in a repository.
- Create a workflow to automate build and test processes.
- Implement a deployment step to publish your application.

## Requirements
1. **GitHub Repository:** Ensure you have access to a GitHub repository where you can set up GitHub Actions.
2. **GitHub Account:** A GitHub account with necessary permissions to modify workflows.
3. **Sample Project:** A simple Java project with a `pom.xml` file for Maven builds.

## Instructions

### 1. Access the Lab Repository
- **Repository Link:** [Basic CI/CD Pipeline Lab Repository](https://github.com/yourusername/basic-ci-cd-lab)
- **Fork the Repository:** Fork the repository to your GitHub account.

### 2. Navigate to GitHub Actions
- Go to the **Actions** tab in your repository.
- Click on **"Set up a workflow yourself"** or choose a starter workflow for Java.

### 3. Create a Workflow File
- **File Path:** `.github/workflows/ci.yml`
- **Content:** *TODO: THIS IS JUST AN EXAMPLE, REQUIRES MORE WORK*
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

### 4. Commit and Push Changes
- Commit the `ci.yml` file to the `main` branch.
- Observe the workflow running in the **Actions** tab.

### 5. Extend the Workflow with Deployment
- **Objective:** Deploy the application after a successful build.
- **Example Deployment to Netlify or Railways:**
    *TODO*
    ```yaml
    - name: Deploy to Netlify
    ```
- **Note:** Adjust the `publish_dir` based on your project's build output.

### 6. Configure Secrets
- Go to **Settings > Secrets > Actions** in your repository.
- Add any necessary secrets (e.g., deployment tokens).

### 7. Test the Pipeline
- Make a commit to trigger the workflow.
- Ensure that build, test, and deployment steps execute successfully.

## Submission
- **Repo link:** Provide the link to your Github (forked) repository.
- **Workflow Link:** Share the link to your GitHub Actions workflow run.
- **Deployment Confirmation:** If applicable, provide a link to your deployed application.

## Troubleshooting
- **Workflow Fails:** Check the logs in the **Actions** tab to identify and fix issues.
- **Deployment Issues:** Ensure that deployment credentials are correctly configured and that the target directory is accurate.

## Additional Resources
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Maven Build Lifecycle](https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html)
- [Deploying with GitHub Actions](https://docs.github.com/en/actions/deployment)

---

# Happy Automating!

Ensure that you understand each step and feel free to reach out if you encounter any issues during the lab. 