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

Archery project has Docker compose file that contains multiple open source tool instance which all are connected with Archery.

Corrently Archery docker-compose has `ZAP Scanner` and `OpenVAS Scanner`. 

```bash
version: '3.6'

services:
  db:
    image: postgres:10.1-alpine
    volumes:
      - postgres_data:/var/lib/postgresql/data/

  archerysec:
    image: archerysec/archerysec:latest
  #  build: .
    command: install.sh
    command: python manage.py runserver 0.0.0.0:8008
    ports:
      - "8008:8008"
    expose:
      - "8008"
    depends_on:
      - db

  zaproxy:
    image: owasp/zap2docker-stable
    command: zap.sh -daemon -host 0.0.0.0 -port 8090 -config api.disablekey=true -config api.addrs.addr.name=.* -config api.addrs.addr.regex=true
    ports:
      - "8090:8090"
    expose:
    # ZAP is running on 8090, we want it to be accessible by our tools
      - "8090"
    links:
      - archerysec

  openvas:
    image: avhost/docker-openvas
    ports:
      - "443:443"
      - "9390:9390"
      - "9392:9392"
    expose:
      - "9390"
      - "9392"
      - "443"
    links:
      - archerysec

volumes:
  postgres_data:
```

Follow below instruction to start Archery docker-compose.

```bash
# Clone Project
$ git clone https://github.com/archerysec/archerysec.git

# Move to directory archerysec
$ cd /archerysec

# Run the docker-compose command.
$ docker-compose up

Open 'http://YOUR_LOCAL_IP:8008' in browser URL for Archery Tool.

Open 'http://YOUR_LOCAL_IP:8090' in browser URL for ZAP API.

Open 'https://YOUR_LOCAL_IP' in browser URL for OpenVAS Scanner.
```



