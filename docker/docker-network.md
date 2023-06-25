#devops 
#containers

### Download and Install

```bash
curl -sSl https://get.docker.com | sh

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


### Portainer

```bash
sudo docker volume create portainer_data

sudo docker pull portainer/portainer-ce:linux-arm

sudo docker run -p 9000:9000 \
--net milky-way \
--ip 172.18.0.2 -it \
--name=portainer \
--restart=always \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data \
-d portainer/portainer-ce:linux-arm64
```

### Show Docker in Portainer (Remote Access)

```bash
# In Remote Docker
sudo mkdir -p /etc/systemd/system/docker.service.d

cd /etc/systemd/system/docker.service.d

sudo nano remote-api.conf

[Service]
ExecStart=
ExecStart=/usr/bin/dockerd -H tcp://0.0.0.0:2375 -H unix://var/run/docker.sock

sudo systemctl daemon-reload
sudo systemctl restart docker
```

### Bitwarden

```bash
sudo docker pull vaultwarden/server:latest

sudo docker volume create bitwarden_data

sudo docker run  -p 8080:80 \
--net milky-way \
--ip 172.18.0.6 \
--name bitwarden \
--restart=always \
-v bitwarden_data:/data \
-v /etc/ssl/certs/:/ssl/ \
-e ROCKET_TLS='{certs="/ssl/bitwarden.crt",key="/ssl/bitwarden.key"}' \
-d vaultwarden/server:latest

-e ROCKET_PORT='81' \
```

### PostgreSQL

```bash
sudo docker pull postgres

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

### PgAdmin

```bash
sudo docker pull dpage/pgadmin4

sudo docker volume create pgadmin_data

sudo docker run -p 5050:5050 \
--name pgadmin \
--restart=always \
-v pgadmin_data:/var/lib/pgadmin \
-e 'PGADMIN_DEFAULT_EMAIL=augustobritodev@gmail.com' \
-e 'PGADMIN_DEFAULT_PASSWORD=' \
-d dpage/pgadmin4

# ARM Version

sudo docker pull biarms/pgadmin4

sudo docker run -p 5050:5050 \
--net milky-way \
--ip 172.18.0.4 \
--name pgadmin \
-v pgadmin_data:/pgadmin \
-e 'PGADMIN_DEFAULT_EMAIL=augustobritodev@gmail.com' \
-e 'PGADMIN_DEFAULT_PASSWORD=' \
-d biarms/pgadmin4
```

### NextCloud

```bash
sudo docker pull nextcloud

sudo docker volume create nextcloud_data

sudo docker run -p 8080:80 \
--name nextcloud \
--restart=always \
-v nextcloud_data:/var/www/html \
-d nextcloud

# If internal error
# /var/www/html/config
chmod -R 777 config.php
```

### Node

```bash
docker pull node

sudo docker volume create node_data

sudo docker run --name node \
--restart=always \
-v node_data:/data \
-d node
```

### Firefly

```bash
sudo docker pull fireflyiii/core:latest

sudo docker volume create firefly_data

sudo docker run  -p 80:8080 \
--net milky-way \
--ip 172.18.0.5 \
--name firefly \
--restart=always \
-v firefly_data:/var/www/html/storage/upload \
-e 'APP_KEY=ebnQSANXiDP3bzMYtjlLtiv2hKFseuUa' \
-e 'APP_URL=http://firefly' \
-e 'DB_HOST=172.18.0.3' \
-e 'DB_PORT=5432' \
-e 'DB_CONNECTION=pgsql' \
-e 'DB_DATABASE=firefly' \
-e 'DB_USERNAME=postgres' \
-e 'DB_PASSWORD=' \
-d fireflyiii/core:latest

APP_KEY = head /dev/urandom | LC_ALL=C tr -dc 'A-Za-z0-9' | head -c 32 && echo
```

### n8n

```bash
docker run -it --rm \
	--name n8n \
	-p 5678:5678 \
	-v ~/.n8n:/home/node/.n8n \
	n8nio/n8n
```
