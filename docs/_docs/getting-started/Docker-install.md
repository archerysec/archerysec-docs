---
title: 
category: Getting Started
chapter: 2
order: 2
---

Deploying with Docker is the easiest and fastest method of getting started. No prerequisites are required other than an modern version of Docker.

ArcherySec Docker is available from [ArcherySec Docker](https://hub.docker.com/r/archerysec/archerysec/)

```bash
$ docker pull archerysec/archerysec
$ docker run -it -p 8000:8000 archerysec/archerysec:latest

# For persistence

docker run -it -p 8000:8000 -v <your_local_dir>:/root/.archerysec archerysec/archerysec:latest

```