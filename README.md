# LARAVEL DOCKER LIGHT
A light docker environment that runs a basic laravel/php solution

# Services
- php-fpm alpine
- mysql
- nginx alpine

# Configuration Steps
- Clone this repository
- Place your source code inside the `src` directory (i.e. place the root of the laravel project inside the src)
- Rename `example-env` to `.env` inorder to be consumed by docker and update the configs as of your taste
- Leave the data directory untouched , the `mysql` database will be mounted here to insure persistance


# Running the container
Inside the `docker` directory issue the commands below

```
docker-compose build
docker-compose up -d
```

# Useful Commands

### Installing composer libraries
Apply the following command inside src folder
```
docker run --rm --interactive --tty \
  --volume $PWD:/app \
  composer install
```

### Applying database migrations
```
docker-compose run php php artisan migrate
```