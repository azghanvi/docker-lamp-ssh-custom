## Docker with LAMP + SSH stack based on Alpine Linux

Really Lightweight 291mb Docker image with lamp, ssh, phpmyadmin (with tunnel access)

## Installation
### Grab from docker hub
```
docker run -d -v /path/to/project:/var/www/localhost/htdocs/ -v /path/to/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=password -p 80:80 -p 3306:3306 --name lamp glats/alpine-lamp

```

### Run you own image

```
git clone https://github.com/azghanvi/docker-lamp-ssh-291m && cd docker-lamp-ssh-291m/
```

### Build the image
```
docker build -t azg/docker-lamp-ssh-291m .
```

### Run it

```
docker run --name container1 -d -p 41061:22 --expose 80 -e MYSQL_ROOT_PASSWORD=root -e SSH_ROOT_PASSWORD=test azg/docker-lamp-ssh-291m

```

or if you have setup nginx-proxy:

```
docker run --name container1 -d -p 41061:22 --expose 80 -e MYSQL_ROOT_PASSWORD=root -e SSH_ROOT_PASSWORD=test -e VIRTUAL_HOST=domain.com --net nginx-proxy azg/adocker-lamp-ssh-291m

```
You can adjust MYSQL_ROOT_PASSWORD, SSH_ROOT_PASSWORD, VIRTUAL_HOST and container name.
