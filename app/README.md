# CI/CD Support Lab

A hands-on CI/CD and production support lab demonstrating automated testing, build processes, Docker, GitHub Actions, Jenkins, and deployment troubleshooting.

## Application

The application is a simple Node.js HTTP server.

### Health Check

```text
GET /health
```

Returns:

```json
{"status":"OK"}
```

## CI with GitHub Actions

GitHub Actions automatically:

1. Checks out the repository
2. Installs Node.js dependencies
3. Runs Jest tests
4. Builds the application artifact
5. Uploads the build artifact
6. Builds the Docker image

Workflow:

```text
.github/workflows/ci.yml
```

## Jenkins

A local Jenkins server was configured to perform CI independently of GitHub Actions.

The Jenkins job:

1. Checks out the GitHub repository
2. Installs application dependencies
3. Runs Jest tests
4. Builds the Docker image

Jenkins runs locally in Docker and uses the Docker Desktop daemon to build containers.

## Docker

The application is packaged using the Dockerfile in this directory.

Build:

```bash
docker build -t cicd-support-app .
```

Run:

```bash
docker run -d --name cicd-support-container -p 3001:3000 cicd-support-app
```

Test:

```bash
curl http://localhost:3001/health
```

## Support Engineering Exercises

This lab has also been used to practice:

* CI failure diagnosis
* Reading build logs
* Test failures and exit codes
* Docker container troubleshooting
* Docker image architecture problems
* Application health checks
* Deployment failures
* Rollback to a known-good image
* Jenkins environment and permission troubleshooting

## Technologies

* Git
* GitHub
* GitHub Actions
* Jenkins
* Node.js
* npm
* Jest
* Docker
* Docker Desktop
* AWS EC2
* GitHub Container Registry
* Linux
* Bash

## Purpose

The purpose of this lab is to build practical hands-on experience troubleshooting software delivery and infrastructure problems from the perspective of a technical support, application support, and SRE-oriented engineer.

