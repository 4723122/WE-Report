@4723122 ➜ /workspaces/WE-Docker (main) $ docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                                         NAMES
9b9d5848b65b   postgres:15    "docker-entrypoint.s…"   34 seconds ago   Up 34 seconds   5432/tcp                                      we-docker-db-1
3769ec71ec1d   4f1b991921c8   "uvicorn main:app --…"   42 minutes ago   Up 42 minutes   0.0.0.0:8000->8000/tcp, [::]:8000->8000/tcp   my-fastapi-container
