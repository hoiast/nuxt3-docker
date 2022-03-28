# Nuxt 3 Docker 

A minimal set for developing a [Nuxt 3](https://v3.nuxtjs.org/docs) app using [Docker](https://docs.docker.com/) in a WSL environment. Despite the little twerks to prevent WSL issues, this minimal set is perfectly suitable for developing under "pure" Linux environments.

This repo is built upon a [minimal set for Nuxt 3](https://v3.nuxtjs.org/getting-started/installation) and includes a Dockerfile and a docker-compose.yml. These files are used to setup an image and a container, respectively.

## Setup

Compose your container and it should start a development server on http://localhost:3000.

```bash
docker compose up -d
```

**Note:** A separate volume is created to isolate dependencies i.e. node_modules. Sharing dependencies over different OS may break your app. As this Docker Image is built over [Alpine](https://alpinelinux.org/), linux users may ignore this warning. 

**Note 2:** A specific environment variable CHOKIDAR_USEPOLLING is set to **true** in Dockerfile to avoid file watching issues when developing using *WSL*. 


