# :rainbow: docker_laravel :cloud_with_lightning_and_rain:
Fresh laravel project in docker.

---

## Settings

Set your mysql database credentials in the **/env/mysql.env** and **/env/phpmyadmin.env** files.


## Commands

>`cd docker_laravel` *go to project directory.*

>`mkdir src` *create new 'src' directory*

Composer:<br />
`docker-compose run --rm composer [...]`
>`docker-compose run --rm composer create-project --prefer-dist laravel/laravel .` *create new laravel project.*

Artisan:<br />
`docker-compose run --rm artisan [...]`
>`docker-compose run --rm artisan migrate` *run migrations.*

Start laravel application:<br />
`docker-compose up -d --build server`

Start laravel application and phpmyadmin:<br />
`docker-compose up -d --build server phpmyadmin`

Stop laravel application:<br />
`docker-compose down`



npm:<br />
`docker-compose run --rm npm [...]`
>**_E.g._** `docker-compose run --rm npm ls` *list installed modules.*
