# Dockerize React Application

Boilerplate files for deploying simple React application in production using Docker.

## Requirements

- Separate running container with **jwilder/nginx-proxy** (using external rev-proxy network).

## Installation

Copy/clone repository into the main application's directory:

```
...
- build
- docker-react-production
  - docker-compose.yml.example
  - Dockerfile.example
  - .env-app.example
  - .env.example
  - .env-webserver.example
  - nginx.conf.example
- .git
- .gitignore
- package.json
- public
- README.md
- src
...
```

Rename `docker-react-production` directory to `docker-production`.

Edit all `*.example` files and rename them by deleting `.example` extentions.

## Deploying app

In the main app's directory

```
docker build -t mynick/my-app-name:1.0.0 -f docker-production/Dockerfile .
```

Then enter the docker-production directory

```
cd docker-production
```

Update the app image name in the docker-compose.

Build React app

```
docker-compose up build
```

Then start the webserver

```
docker-compose up -d webserver
```
