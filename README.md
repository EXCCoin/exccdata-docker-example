# Exccdata docker example

This repository is an example how to start a full Exccdata instance using Docker.

## Requirements
- Docker
- OpenSSL
- Docker Compose (optional)

## Usage
First you need to create a certificate for Exccd daemon RPC, you can create a self-signed certificate using OpenSSL with
following command: `openssl req -x509 -newkey rsa:4096 -keyout conf/exccd.key -out conf/exccd.cert -days 365 -subj '/CN=exccd' -nodes`.
Then you can start services using `docker stack deploy` or `docker-compose`. Please be aware first start of Postgres service
may take longer due to database initialization and cause problems with connecting Exccdata to Postgres. If you encounter
this problem, please restart Exccdata service.
