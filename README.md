# :rainbow: docker_laravel :cloud_with_lightning_and_rain:
Fresh *laravel* project in *docker*.

---

## How to start

Clone the project to a local machine:
>`git clone https://github.com/ramasd/docker_laravel.git`

- Go to project directory:
>`cd docker_laravel`

- Set the wanted *mysql* database credentials in the **/env/mysql.env**. I.e.,
```
MYSQL_DATABASE=homestead
MYSQL_USER=homestead
MYSQL_PASSWORD=secret
MYSQL_ROOT_PASSWORD=secret
```
- Set the *phpmyadmin* credentials in the **/env/phpmyadmin.env**. I.e.,
```
PMA_HOST=db           #[database service name from docker-compose.yaml file]
PMA_USER=homestead    #[mysql.env MYSQL_USER value]
PMA_PASSWORD=secret   #[mysql.env MYSQL_PASSWORD value]
```


- Create new *src* directory:
>`mkdir src`

- Create new *laravel* project:
>`docker-compose run --rm composer create-project --prefer-dist laravel/laravel .`

- Set database environment values in the **/src/.env** file:
```
DB_CONNECTION=mysql
DB_HOST=db              #[database service name from docker-compose.yaml file]
DB_PORT=3306
DB_DATABASE=homestead   #[mysql.env MYSQL_DATABASE value]
DB_USERNAME=homestead   #[mysql.env MYSQL_USER value]
DB_PASSWORD=secret      #[mysql.env MYSQL_PASSWORD value]
```

- Start *laravel* application and *phpmyadmin* containers:
>`docker-compose up -d --build server phpmyadmin`

`http://localhost:8000` - *laravel* app <br />
`http://localhost:8080` - *phpmyadmin*

- Stop running containers
>`docker-compose down`

---

## Commands

**composer**:<br />
`docker-compose run --rm composer [...]`
>**_I.e._,** `docker-compose run --rm composer update` *updates all outdated commands.*

**artisan**:<br />
`docker-compose run --rm artisan [...]`
>**_I.e._,** `docker-compose run --rm artisan migrate` *runs migrations.*

**npm**:<br />
`docker-compose run --rm npm [...]`
>**_I.e._,** `docker-compose run --rm npm ls` *lists installed modules.*
