﻿# prom-mirth-channel-exporter

Run it via docker-compose.
Create a .env file for the environment  variables in the same folder where your docker-compose.yaml is stored

## sample of .env-file
```
MIRTH_ENDPOINT=https://yourmirthserver:port
MIRTH_USERNAME=your mirth user
MIRTH_PASSWORD=your password
```

## sample of docker-compose.yml
```
version: "3"
services:
  mirthexporter:
    image: dspkd\prom-mirth-channel-exporter:latest
    container_name: mirth-channel-exporter
    restart: always
    ports:
      - '9141:9141'
    environment:  
      - MIRTH_ENDPOINT=${MIRTH_ENDPOINT}
      - MIRTH_USERNAME=${MIRTH_USERNAME}
      - MIRTH_PASSWORD=${MIRTH_PASSWORD}
```
