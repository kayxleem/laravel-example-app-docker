# ![Laravel RealWorld Example App](.github/readme/logo.png)



# Installation with docker

## Prerequisites

#### 1. A ubuntu operating system 
#### 2. docker installed

## Step1 - Clone the repository and change directory


## Step2 - create the env file from env example and edit the necessary variables

cp .env.example .env

DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=yourusername
DB_PASSWORD=yourpassword


## Step 3 - Build your app

docker-compose build 

## Step 4  When the build is finished, you can run the environment in background mode with:

$ docker-compose up -d









For more information on how to this works with other frontends/backends, head over to the [RealWorld](https://github.com/gothinkster/realworld) repo.

## How it works

The API is built with [Laravel](https://laravel.com/), making the most of the framework's features out-of-the-box.

The application is using a custom JWT auth implementation: [`app/Jwt`](./app/Jwt).

## Getting started

The preferred way of setting up the project is using [Laravel Sail](https://laravel.com/docs/sail),
for that you'll need [Docker](https://docs.docker.com/get-docker/) under Linux / macOS (or Windows WSL2).

### Installation

Clone the repository and change directory:

    git clone https://github.com/f1amy/laravel-realworld-example-app.git
    cd laravel-realworld-example-app

Install dependencies (if you have `composer` locally):

    composer create-project

Alternatively you can do the same with Docker:

    docker run --rm -it \
        --volume $PWD:/app \
        --user $(id -u):$(id -g) \
        composer create-project

Start the containers with PHP application and PostgreSQL database:

    ./vendor/bin/sail up -d

(Optional) Configure a Bash alias for `sail` command:

    alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'

Migrate the database with seeding:

    sail artisan migrate --seed

## Usage

The API is available at `http://localhost:3000/api` (You can change the `APP_PORT` in `.env` file).

### Run tests

    sail artisan test

### Run PHPStan static analysis

    sail php ./vendor/bin/phpstan

### OpenAPI specification (not ready yet)

Swagger UI will be live at [http://localhost:3000/api/documentation](http://localhost:3000/api/documentation).

For now, please visit the specification [here](https://github.com/gothinkster/realworld/tree/main/api).

## Contributions

Feedback, suggestions, and improvements are welcome, feel free to contribute.

## License

The MIT License (MIT). Please see [`LICENSE`](./LICENSE) for more information.
