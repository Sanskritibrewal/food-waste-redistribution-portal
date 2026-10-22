
# Food Waste Tracking and Redistribution Portal

## Project Overview
This project demonstrates a portal for tracking surplus food
from university canteens and nearby restaurants and coordinating
its redistribution to community organizations.

## Features
- Sample surplus food records
- Food quantities and collection deadlines
- Pickup locations and participating organizations
- Available, reserved, collected, and redistributed statuses
- Summary dashboard

## Technologies
- HTML and CSS
- JavaScript
- Git and GitHub
- Jenkins
- Docker
- Kubernetes
- Nginx

## Continuous Integration and Deployment
Jenkins retrieves the source code, validates project files,
builds and tests a Docker image, publishes the image to Docker Hub,
and deploys the application to Kubernetes.

The pipeline supports parallel validation, parameterized builds,
conditional execution, and archived build artifacts.

## Rollback Demonstration
A parameterized Jenkins build can deploy a deliberately nonexistent
image tag. When the rollout fails, Jenkins runs
`kubectl rollout undo` to restore the previous stable revision.

The restored application is verified using Kubernetes rollout
status and a browser check.

## Local Access
Use the following command to access the Kubernetes application:

`kubectl port-forward service/food-waste-portal 8082:80`

Open http://localhost:8082 in a browser.

## Limitations
This academic prototype uses sample records stored in the frontend.
It does not include a backend database, authentication, or live
food collection integrations.
