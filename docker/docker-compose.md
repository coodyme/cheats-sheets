#docker 
# Docker e Docker Compose do zero ao Deploy

Category: Containers, Docker
Last edited time: July 22, 2022 1:41 PM

# Docker

# Docker Compose

# Copy files

```bash
# From Docker to Host
docker cp <containerId>:/file/path/within/container /host/path/target

# From Host to Docker
docker cp /host/path/target <containerId>:/file/path/within/container
```

# Execute console

```bash
docker exec -it <container_id_or_name> ./bin.bash
```