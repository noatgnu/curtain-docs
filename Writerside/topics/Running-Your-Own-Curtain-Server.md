# Running Your Own Curtain Server (Backend)

If you are interested, you can also run your own Curtain server. This section will give you the information needed to run
your own Curtain server with S3 compatible storage backend.

## Requirements

Hardware:
- 4GB RAM
- 2 CPU cores
- 100GB storage

Software:
- Python 3.9 or above
- NodeJS 20.9 or above
- Docker and Docker Compose

## Backend Installation (Docker)

### Clone the repository

```bash
git clone https://github.com/noatgnu/curtainbe.git
```

### Build the backend docker image

```bash
docker build . -t curtainbe -f docker/Dockerfile
```

### Run the backend using docker compose

Create a `.env` file in the root directory of the repository with the following content:

```bash
AWS_ACCESS_KEY_ID=your_aws_access_key_id
AWS_S3_ENDPOINT_URL=your_aws_s3_endpoint_url
AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key
AWS_STORAGE_BUCKET_NAME=your_aws_storage_bucket_name
CURTAIN_ALLOW_NON_STAFF_DELETE=0
CURTAIN_ALLOW_NON_USER_POST=1
CURTAIN_DEFAULT_USER_CAN_POST=1
CURTAIN_DEFAULT_USER_LINK_LIMIT=0
DJANGO_ALLOWED_HOSTS=list_of_allowed_hostnames
DJANGO_CORS_WHITELIST=list_of_allowed_hostnames_with_protocol
ORCID_OAUTH_CLIENT_ID=your_orcid_oauth_client_id
ORCID_OAUTH_SECRET=your_orcid_oauth_secret
POSTGRES_DB=postgres
POSTGRES_HOST=curtaindb
POSTGRES_NAME=postgres
POSTGRES_PASSWORD=your_postgres_password
POSTGRES_USER=postgres
POSTGRES_PORT=5432
POSTGRES_SSL=0
REDIS_DB=0
REDIS_HOST=redis
REDIS_PASSWORD=your_redis_password
REDIS_PORT=6379
SECRET_KEY=your_django_secret_key
STORAGE_BACKEND=s3
WORKING_ENV=PRODUCTION
DEBUG=False
```

Then create a `docker-compose.yml` file in the root directory of the repository with the following content:

```yaml
version: "3.8"
services:
    curtainweb:
        container_name: curtainweb
        image: curtainbe
        restart: always
        #ports:
        #    - "8000:8000"
        env_file:
            - .env
        depends_on:
            - curtaindb
            - redis
        networks:
            - curtain
    curtainwebworker:
      container_name: curtainwebworker
      image: curtainbe
      restart: always
      command: /bin/sh -c "python manage.py runworker default"
      #ports:
      #  - "8000:8000"
      env_file:
        - .env
      depends_on:
        - curtaindb
        - redis
      networks:
        - curtain
    curtaindb:
        container_name: curtaindb
        image: postgres:14.5
        restart: always
        env_file:
            - .env
        volumes:
            - curtaindb:/var/lib/postgresql/data
        networks:
            - curtain
    redis:
        container_name: redis
        image: redis:latest
        restart: always
        command: /bin/sh -c "redis-server --requirepass $$REDIS_PASSWORD"
        env_file:
            - .env
        volumes:
            - redis:/data
        networks:
            - curtain
networks:
    curtain:    
```

Then run the following command to start the backend:

```bash
docker-compose up -d
```

