# Docker LEMP

- Nginx 1.20
- PHP 7.4
- MariaDB 10.6

## Setup

- Create and configure an *.env* file from *.env.dist*
- Build containers:
  
  ```
  docker-compose build
  ```

- Start containers: `docker-compose up`
 ```
  docker-compose up -d
  ```

## Change hostname

- Edit `nginx/default.conf` and change the parameter **server_name**.

```
server_name my-project.local
```

- Edit hosts file and the line.

```
127.0.0.1  my-project.local
```

## Change root folder server

- Edit `nginx/default.conf` and change the parameter **root**.
