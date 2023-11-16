# docker-compose-laravel
Environment for laravel applications

## Getting Started
Available for versions `7.X` and `8.X` of the Laravel Framework.

## Deploy containers
```shell
- docker-compose up -d --build
```

## Directory structure
```
├── app
├── configs
│   └── mysql
├── data
│   ├── logs
│   └── mysql
├── dockerfiles
│   └── php
│        └── Dockerfile
├── docker-compose.yml
└── README.md
```

## Usage
clone your application in the `app` directory and mount the server with the following command:
```shell
docker exec -it php_app php artisan serve --host=0.0.0.0 --port=8000
```



