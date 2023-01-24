# Docker LEMP Stack
## _Simple LEMP Stack for local servers_

## Features

- Nginx
- PHP (7.4, 8.0 & 8.1) and Composer
- MySQL
- MongoDB
- PhpMyAdmin
- Everything in docker containers

## Installation

Docker LEMP Stack requires [Docker](https://docs.docker.com/engine/install/)

First create a file in the following path: `data/vhost/default/index.html`. It will be the page that will be displayed by default. If you don't have a html file to use, you can use this:
```html
<!DOCTYPE html>  
<html lang="en">  
<head>  
	<title>DEFAULT DOMAIN</title>
    <style>
        body {
            background: black;
            color: hotpink;
        }
    </style>
</head>
<body>
	This is default domain
</body>
</html>
```

Then:

```sh
cd docker-lemp-stack
docker compose up -d
```
That's all, if you go to [localhost](http://localhost/) you will see the page of the html file you created.

## SSL

You can use OpenSSL to self-certify your domains, below are links to the guides for each operating system:

. [Windows](data/nginx/certs/WINDOWS.md)

## TODO

- Cert guides for Linux/Mac

## License

MIT

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

[Docker]: <https://www.docker.com/>
[php]: <https://www.php.net/>
[nginx]: <https://www.nginx.com/>
[MySQL]: <https://www.mysql.com/>
[phpMyAdmin]: <https://www.phpmyadmin.net/>
[OpenSSL]: <https://www.openssl.org/>
