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
