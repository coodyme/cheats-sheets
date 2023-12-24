#devops 
#docker
#cli

### Download and Install
```bash
curl -sSl <https://get.docker.com> | sh

docker run hello-world
```

### Change Network IP
```bash
docker network disconnect [OPTIONS] NETWORK CONTAINER
docker network connect --ip 192.168.150.3 NETWORK CONTAINER
```

### Docker Network
```bash
docker network create --subnet=172.18.0.0/16 --gateway=172.18.0.1 network-name
```

# Containers
You can create container using Docker CLI, but are recommended to use docker-compose

For example we can create a container for PostgreSQL
```bash
sudo docker pull postgres
```

```bash
```

```bash
```


```bash


sudo docker volume create postgres_data

sudo docker run -p 5432:5432 \
--net milky-way \
--ip 172.18.0.3 \
--name postgres \
--restart=always \
-v postgres_data:/var/lib/postgresql/data \
-e 'POSTGRES_PASSWORD=' \
-e 'POSTGRES_DB=postgres' \
-d postgres
```

## Remove all images
```bash
docker rmi $(docker image ls -aq) -f
```

## Force build
```bash
docker-compose up -d --build
```