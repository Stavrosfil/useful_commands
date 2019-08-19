# Useful Bash Commands

This is a collection of useful bash commands I have found over time.

## Docker

### The docker containers are awesome!

* Login inside a Docker Container with admin rights, and an interactive terminal.

``` bash
docker exec -u 0 -it container_name /bin/bash
```

* Alternatively, you can use `sh` inside the container.

``` bash
docker exec -u 0 -it container_name /bin/sh
```

