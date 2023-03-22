# Docker for php 7.1

## Prefences:
- PHP 7.1
- Nginx Alphine
- NodeJS 12.x
- Extentions for php

## Example Structure Folder:
```
|--- Base Folder/
|    |--- Your Project/
|    |    |--- app/
|    |    |--- bootstrap/
|    |    |--- config/
|    |    |--- ...
|    |--- docker/
|    |    |--- nginx/
|    |    |--- php/
|    |    |--- docker-compose.yml
```

## Usage:
- Clone this repository:
  `$ git clone [url] [folder name]`
- Go to folder:
  `$ cd [folder name]`
- Copy file `.env.example` to `.env` and edit it:
  `$ cp .env.example .env`
- Run docker:
  `$ docker-compose up -d`
- Workspace:
  `$ docker-compose exec php bash`
- Done!

## Run with server name:
- Access server name to file (ubuntu) `/etc/hosts`
- Access server name to file (mac os) `/private/etc/hosts`
- Access server name to file (windows) `C:\Windows\System32\drivers\etc\hosts`
- Add line:
  `127.0.0.1 laravel.test`
