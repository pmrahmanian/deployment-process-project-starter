# CircleCI CI/CD Pipeline Description

## Diagram
![CircleCI Pipeline Diagram](./CI-CD-Pipeline.png?raw=true "CircleCI Pipeline Diagram")

## Overview

The CI/CD pipeline is set up into three processes in CircleCI. The pipeline is triggered by pushed commits to the github repo and has the following phases:
- Build (CI)
- Hold
- Deploy (CD)

### Build (Continuous Integration)
The build phase of our pipeline represents the continuous integration workflow. There are many steps involved here, categroized into four main parts:
- Setup
- Dependency Injection
- Linting
- Building

**Setup**
The CI process starts by spinning up an Elastic Beanstalk environment and preparing the environment variables. It then installs Node.js before checking out the code.

**Dependency Injection**
The next step in the process installs both the frontend app dependencies as well as the backend api dependencies.

**Linting**
Next the frontend code gets linted.

**Building**
Finally both the Frontend app and backend api get built.

### Hold
At this stage of the pipeline, CI has completed. The pipeline is paused to allow for manual approval before continuing on to CD.

### Deploy (Contionuous Deployment)
The Deploy phase of our pipeline represents the continuous deployment workflow. There are many steps involved here, categroized into four main parts:
- Environment Setup
- CLI Setup
- Checkout
- Deployment

**Environment Setup**
The CD process starts by spinning up an Elastic Beanstalk environment and preparing the environment variables. It then installs Node.js.

**CLI Setup**
Next, both the Elastic Beanstalk and AWS CLIs are setup and configured with the AWS Access Keys.

**Checkout**
The Code is checked out.

**Deployment**
The backend API gets deployed via Elastic Beanstalk and the frontend is deployed to the S3 Bucket.
