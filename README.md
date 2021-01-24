## Docker with LAMP + SSH stack based on Alpine Linux

Really Lightweight 291mb Docker image with lamp, ssh, phpmyadmin (with tunnel access)

## Installation
### Grab from docker hub
```
docker run -d -v /path/to/project:/var/www/localhost/htdocs/ -v /path/to/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=password -p 80:80 -p 3306:3306 --name lamp glats/alpine-lamp
```

### Run you own image

```
git clone https://github.com/azghanvi/docker-291M-lamp-ssh-alpine && cd docker-291M-lamp-ssh-alpine/
```

### Build the image
```
docker build -t azg/alpine-lamp-ssh .
```

### Run it

```
docker run -d -v /path/to/project:/var/www/localhost/htdocs/ -e MYSQL_ROOT_PASSWORD=password -p 80:80 -p 3306:3306 --name lamp $USER/alpine-lamp
```

### Connect to MariaDB
To use this you need to install mysql/mariadb cli client
```
mysql -uroot -ppassword -h 127.0.0.1
```

### PhpMyAdmin

If you want to use phpMyAdmin use the branch called: **phpmyadmin-feature**
