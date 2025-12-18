# docker-compose



```
docker-compose up --scale worker=5
```

```
version: '3.8'
services:
  redis:
    image: redis:7-alpine

  web:
    build: .
    ports:
      - "8000:8000"

  worker:
    build: .
    command: celery -A app.tasks worker
```