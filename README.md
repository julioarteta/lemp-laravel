docker-lemp
===========

* Nginx
* PHP 7.2-fpm
* Mariadb
* PHPMyAdmin

Setup Docker and Docker Compose
===========

You need to have [Docker](https://docs.docker.com/install/linux/docker-ce/ubuntu/)  and [Docker compose ](https://docs.docker.com/compose/install/#install-compose)  installed on your machine.


### Install your app

- Create directory **[project-name]** and clone the docker-lemp repository inside
```
mkdir [project-name]
cd /[project-name]
git clone git@gitlab.com:julioarteta/docker-lemp.git .

```

- Create directory **htdocs** inside of your project folder and set permissions
```
mkdir htdocs
sudo chmod -R 775 htdocs/
```

- Add current user to docker group (linux only)
```
sudo usermod -aG docker "$(whoami)"
```

- Set hostname
```
vim docker-lemp/etc/nginx/default.conf
server_name  [project-name]
```

- Add host to your local maschine
````
sudo vi /etc/hosts
127.0.0.1    [project-name]
````

- Start Docker 
```
docker-composer build
docker-compose up
```


