# Useful Bash Commands

This is a collection of useful bash commands I have found over time.

## Docker

> Login inside a `docker container` with `admin` rights, and an `interactive terminal`

``` bash
> docker exec -u 0 -it container_name /bin/bash
```

> Alternatively, you can use `sh` inside the container

``` bash
> docker exec -u 0 -it container_name /bin/sh
```

## Networking

> Get web `port` usage of every service using it

``` bash
> sudo lsof -itcp

COMMAND     PID     USER    FD  TYPE    DEVICE      SIZE/OFF    NODE    NAME
docker-pr   20887   root    4u  IPv6    225535203   0t0         TCP     *:1883 (LISTEN)
```

> Generate strong `ssh key` for server setup

```bash
>  ssh-keygen -t rsa -b 4096
```

## Files

> Show `files size` in a directory and `sort by size`

```bash
> du -csh * | sort -rh

# du: Disk Usage
# -s: Summary for each file
# -h: Human readable format
# -c: Produce grand total

> du -csh * | sort -rh | head -n10

# head -n10: Reduces the output to only 10 rows for readability
```

> Change all `file permissions` on current directory to `current user` rights

```Bash
# cd /path/to/my/files

> chown -R $USER:$USER .
```