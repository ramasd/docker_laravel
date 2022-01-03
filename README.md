# :rainbow: docker_laravel :cloud_with_lightning_and_rain:
Fresh *laravel* project in *docker*.

---

## How to start

- Set the wanted mysql database credentials in the **/env/mysql.env** and **/env/phpmyadmin.env**.

- Go to project directory:
>`cd path_to_docker_laravel_project`

- Create new *src* directory:
>`mkdir src`

- Create new *laravel* project:
>`docker-compose run --rm composer create-project --prefer-dist laravel/laravel .`

- Set values in the **/src/.env** file:
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

`localhost:8000` - *laravel* app <br />
`localhost:8080` - *phpmyadmin*

- Stop running containers
>`docker-compose down`

---

## Commands

**composer**:<br />
`docker-compose run --rm composer [...]`
>**_E.g._** `docker-compose run --rm composer update` *updates all outdated commands.*

**artisan**:<br />
`docker-compose run --rm artisan [...]`
>**_E.g._** `docker-compose run --rm artisan migrate` *runs migrations.*

**npm**:<br />
`docker-compose run --rm npm [...]`
>**_E.g._** `docker-compose run --rm npm ls` *lists installed modules.*
