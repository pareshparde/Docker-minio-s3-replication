# Docker-minio-s3-replication
A Docker Compose setup for free open-source Amazon S3 compatible object storage with automatic site replication using MinIO.

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

2. **Configure Environment Variables:**

    Create a `.env` file in the root directory and set the necessary environment variables. Example:

    ```bash
    MINIO_ACCESS_KEY=minioadmin
    MINIO_SECRET_KEY=minioadmin
    ```

3. **Start the Services:**

    ```bash
    docker-compose up -d
    ```

4. **Access MinIO Console:**

    Open your web browser and go to `http://localhost:9001`. Log in with the access key and secret key you set in the `.env` file.
