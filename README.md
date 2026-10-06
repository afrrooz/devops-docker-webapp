# DevOps Docker Web App

A simple Node.js + Express web application created to practice:

- Git and GitHub
- Docker
- Docker Hub
- GitHub Actions
- CI/CD

## Run locally

```bash
npm install
npm start
```

Open:

http://localhost:3000

## Run with Docker

Build:

```bash
docker build -t devops-webapp .
```

Run:

```bash
docker run -d --name devops-webapp -p 3000:3000 devops-webapp
```

Open:

http://localhost:3000

## GitHub Actions setup

Add these GitHub repository secrets:

- `DOCKERHUB_USERNAME` = your Docker Hub username
- `DOCKERHUB_TOKEN` = your Docker Hub access token

Then push the project to the `main` branch.

GitHub Actions will:

1. Checkout the repository
2. Set up Docker Buildx
3. Log in to Docker Hub
4. Build the Docker image
5. Push `latest` and the Git commit SHA tag

## Docker Hub image

After a successful workflow, your image will be:

```text
YOUR_DOCKERHUB_USERNAME/devops-webapp:latest
```

Pull it with:

```bash
docker pull YOUR_DOCKERHUB_USERNAME/devops-webapp:latest
```
#docker credentials added in secrets