# FastAPI CRUD on EC2 with Docker

## Run locally

```bash
docker build -t fastapi-crud:latest .
docker run -d --name fastapi-crud -p 8000:8000 -v $(pwd)/data:/app/data --restart unless-stopped fastapi-crud:latest
```

## Test

```bash
curl http://localhost:8000/health
curl -X POST http://localhost:8000/items -H "Content-Type: application/json" -d '{"title":"First item","description":"Hello"}'
curl http://localhost:8000/items
```
