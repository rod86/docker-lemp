# Docker LEMP

- Nginx 1.21
- PHP 8.1
- MariaDB 10.6.7

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

## Debug

### PHPStorm

- In Preferences, go to *PHP > Debug*, configure the debug port and IDE key to the ones defined in `php/xdebug.ini`.

- Start listening in PHPStorm

- Enable debuging in browser with the debug bookmarks or XDebug plugin.

- Send request

- In the first debug, you will be asked to map your local project with server path.

[PHPStorm Zero Config Debug](https://www.jetbrains.com/help/phpstorm/2021.3/zero-configuration-debugging.html)

[Browser debugging extensions](https://www.jetbrains.com/help/phpstorm/2021.3/browser-debugging-extensions.html)

[Start/Stop debug bookmarks](https://www.jetbrains.com/phpstorm/marklets/)

### Enable/Disable debugging from API clients

#### Start

Attach the paremeter ```XDEBUG_SESSION_START``` in the url with the IDE key as value.

```
curl --location --request GET 'http://localhost?XDEBUG_SESSION_START=PHPSTORM'
```

#### Stop

Attach the paremeter ```XDEBUG_SESSION_STOP``` in the url with the IDE key as value.

```
curl --location --request GET 'http://localhost?XDEBUG_SESSION_STOP=PHPSTORM'
```
