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
