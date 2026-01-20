# Deployment Documentation: ToDo Application

## Artifact Information
**Repository:** `d4vp/todoapp`
**Tag:** `1.0.0`
**Registry:** [Docker Hub Link](https://hub.docker.com/r/d4vp/todoapp)

---

## Deployment Lifecycle

### 1. Build Process
Initialize the build stage to generate the local image artifact. This process includes dependency installation and database migration.

```bash
docker build -t todoapp .
2. Runtime Execution
Execute the container instance mapping host port 8081 to container port 8000.

Option A: Run from Local Build

Bash

docker run -p 8081:8000 todoapp
Option B: Pull from Remote Registry (Docker Hub)

Bash

docker run -p 8081:8000 d4vp/todoapp:1.0.0
3. Application Access
Verify the deployment status by accessing the application interface:

URL: http://localhost:8081

Troubleshooting
Error: Port Allocation Failure If port 8081 is occupied, terminate existing containers:

Bash

docker rm -f $(docker ps -aq)