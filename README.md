# Docker MinIO S3 Replication

This repository contains a Docker Compose setup for an open-source Amazon S3 compatible object storage solution using MinIO. It includes automatic site replication across multiple MinIO instances.

## Features

- **Amazon S3 Compatible:** Fully compatible with Amazon S3 API.
- **Site Replication:** Automatic replication across multiple MinIO instances for high availability.
- **Dockerized Deployment:** Easy to deploy using Docker Compose.

## Prerequisites

- Docker
- Docker Compose

## Setup

1. **Clone the repository:**

    ```bash
    git clone https://github.com/yourusername/docker-minio-s3-replication.git
    cd docker-minio-s3-replication
    ```

2. **Create the `init.sh` Script:**

    Create an `init.sh` script in the root directory with the following content:

    ```bash
    #!/bin/bash
    mc alias set minio1 http://minio1:9000 admin password
    mc alias set minio2 http://minio2:9000 admin password
    mc alias set minio3 http://minio3:9000 admin password

    mc mb minio1/mybucket
    mc replicate add minio1/mybucket --remote-bucket mybucket --arn minio2
    mc replicate add minio1/mybucket --remote-bucket mybucket --arn minio3
    ```

    Make the script executable:

    ```bash
    chmod +x init.sh
    ```

3. **Start the Services:**

    ```bash
    docker-compose up -d
    ```

4. **Access MinIO Console:**

    Open your web browser and go to `http://localhost:9000`. Log in with the access key and secret key `admin` and `password`.


