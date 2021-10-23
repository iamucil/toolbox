# Laravel toolbox

Use this configuration for laravel web app.  
User laravel framework as web app.  

Clone this repository, and copy `laravel` directory for start developing in your local machine. Make sure you already has `docker` installed on your machine.  

## Init laravel web app 

Run this command from root directory (this directory).  
```bash 
docker run --rm -i -t -v $(pwd)/app:/app --workdir=/app composer \
    composer composer create-project laravel/laravel web
```

This command will generate laravel app called web inside app directory. 

## MariaDB database (docker) 

Create directory `mariadb/data` inside `var` directory. This directory are used for persistent data for mariadb image. Inspect `docker-compose.yaml` file, for more details read manuals on mariadb docker hub.

## Running all service 

Just run `docker-compose up`, all services defined in `docker-compose.yaml` will be run. Inspect docker services using `docker ps`. Access `localhost:8080` from your favorite browser.