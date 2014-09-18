nginx docker
============

This Dockerfile was based off:
https://github.com/dockerfile/nginx

This repository contains **Dockerfile** of [Nginx](http://nginx.org/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/nvitius/nginx/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).


### Base Docker Image

* [phusion/baseimage-docker](http://phusion.github.io/baseimage-docker/)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://registry.hub.docker.com/u/nvitius/nginx/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull nvitius/nginx`

   (alternatively, you can build an image from Dockerfile: `docker build -t="nvitius/nginx" github.com/nvitius/nginx`)


### Usage

    docker run -d -p 80:80 nvitius/nginx

#### Attach persistent/shared directories

    docker run -d -p 80:80 -v <sites-enabled-dir>:/etc/nginx/sites-enabled -v <certs-dir>:/etc/nginx/certs -v <log-dir>:/var/log/nginx nvitius/nginx

After few seconds, open `http://<host>` to see the welcome page.

