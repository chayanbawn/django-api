# Api with django 3.0

djangoapi is a key value store api which uses redis to store data.

## Prerequisite
1. docker
2. git

## Installation

Clone the repository from github and run docker-compose up --build

```bash
git clone https://github.com/chayanbawn/django-api.git
cd djangoapi
docker-compose up --build

```

## Adjust TTL

- Update the value of REDIS_TTL environment variable in docker-compose.yml file.

## Usage

1. Get all stored values

```bash
curl localhost:8000/api/values

```

2. Get get values by keys

```bash
curl localhost:8000/api/values?keys=key1

```

3. Post request to save data.

```bash
curl -d '{"key1":"value1", "key2":"value2"}' -H "Content-Type: application/json" -X POST http://localhost:8000/api/values

```

4. Patch request to update data.

```bash
curl -d '{"key1":"value1", "key2":"value2 updated"}' -H "Content-Type: application/json" -X PATCH http://localhost:8000/api/values

```

## Test

```bash
docker exec -it "container id of django-api_web image" /bin/bash
python manage.py test

```

