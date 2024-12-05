# Introduction to CI/CD with GitHub Actions

## Lesson Overview :pencil2: (45 minutes)

In this lesson, we will explore Continuous Integration and Continuous Deployment (CI/CD) and its implementation using GitHub Actions. Through practical examples and explanations, participants will learn how to automate their software development workflow, from code integration to deployment, using GitHub's built-in automation tools. This foundation will prepare students for hands-on experience in setting up their own CI/CD pipelines.

### Lesson Structure
- Introduction and CI/CD Concepts (10 minutes)
- GitHub Actions Explanation and Demonstration (15 minutes)
- Workflow Examples and Discussion (15 minutes)
- Q&A and Lab Transition (5 minutes)

<br>

## Learning Objectives :notebook:

By the end of this lesson, you will be able to:

1. Define CI/CD and explain its importance in modern software development
2. Identify the key components of a CI/CD pipeline and their functions
3. Navigate GitHub Actions interface and understand its core concepts
4. Create a basic GitHub Actions workflow file using YAML syntax
5. Configure automated testing and building steps in a workflow

<br>

## Key Definitions and Examples :key:

### Continuous Integration (CI) Definition

Continuous Integration is a software development practice where developers regularly merge their code changes into a central repository, after which automated builds and tests are run. This practice helps detect and address integration issues early in the development cycle.

<br>

#### CI Example

```yaml
name: CI Example
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Run tests
        run: |
          ./gradlew test
```

This example shows a simple GitHub Actions workflow that runs tests automatically whenever code is pushed to the repository.

<br>

### Continuous Deployment (CD) Definition

Continuous Deployment is the automated process of delivering code changes directly to production after passing through your CI pipeline. It ensures that your software can be reliably released at any time and reduces manual deployment errors.

Common deployment targets include:
- Cloud platforms (AWS, Google Cloud, Azure)
- Container orchestration systems (Kubernetes)
- Platform-as-a-Service (Netlify, Railway, Heroku, DigitalOcean, etc.)
- Self-hosted servers

<br>

#### CD Example

```yaml
name: CD Example
on:
  push:
    branches: [ main ]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Build application
        run: ./gradlew build
      - name: Deploy to production
        run: |
          echo "Deploying application..."
          # Deployment commands here
```

This example demonstrates a basic deployment workflow that triggers automatically when code is pushed to the main branch.

<br>

### GitHub Actions Workflow Definition

A GitHub Actions workflow is a configurable automated process that you can set up in your repository to build, test, package, release, or deploy your project. Workflows are defined using YAML syntax and are stored in the `.github/workflows` directory.

<br>

#### Workflow Example

```yaml
name: Java CI/CD Pipeline
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
      - name: Set up JDK 17
        uses: actions/setup-java@v2
        with:
          java-version: '17'
          distribution: 'adopt'
      - name: Build with Gradle
        run: ./gradlew build
      - name: Run tests
        run: ./gradlew test
```


This example shows a complete CI/CD workflow for a Java application, including setting up the environment, building the project, and running tests.

<br>

## Additional Resources :clipboard: 

If you would like to study these concepts before the class or would benefit from some remedial studying, please utilize the resources below:

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Understanding CI/CD - Martin Fowler](https://martinfowler.com/articles/continuousIntegration.html)
- [GitHub Actions Marketplace](https://github.com/marketplace?type=actions)
- [GitHub Actions Tutorial for Java](https://docs.github.com/en/actions/guides/building-and-testing-java-with-gradle)

> Note: This lesson provides a solid foundation for the subsequent lab session where students will get hands-on experience implementing their own CI/CD pipelines.
