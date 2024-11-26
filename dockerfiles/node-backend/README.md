Run in production mode with docker

first build the image:

```bash
docker build -t node-backed:8 .
```

Run the image

```bash
docker run -d --env-file .env -p 5003:5003 node-backend:8
```
