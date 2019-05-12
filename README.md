# thrx-docker-ntopng-dev

## thrx-ntopng-dev

```
    docker run \ 
    --detach \
    --restart always \
    --net=host \
    --name thrx-ntopng-dev \
    -t -i -v \
    thrx/thrx-ntopng-dev 
```

## Advanced usage


### Reverse Proxy

add:
```
ntopng -Z /ntopng
```

nginx:
```
location /ntopng/ {
      auth_basic "Restricted ntopng"; #For Basic Auth
      auth_basic_user_file /etc/nginx/.htpasswd;  #For Basic Auth
      error_log /var/log/nginx/ntopng.error.log;
      proxy_pass http://192.168.1.4:3000/ntopng/;
}
```


```
http://localhost:3000/ntopng/

https://server/ntopng/
```

### Build from source code

You can build the image also from source. To do this you have to clone the
[thrx-docker-ntopng-dev](https://github.com/thrx-devops/thrx-docker-ntopng-dev) repository from GitHub:

```
docker build --rm --no-cache -t thrx/thrx-ntopng-dev .
```

### Bash shell inside container

If you need a shell inside the container you can run the following command:

```
docker exec -ti ntopng /bin/sh
```
