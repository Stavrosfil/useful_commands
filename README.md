# Useful Commands

This is a collection of useful commands I have found over time.

## Docker

> Stop all the active containers at once and

```bash
> docker stop $(docker ps -q)
```

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

> Convert windows line endings to unix

```bash
dos2unix file.txt
```

> Change `ownership` of all files on current directory to `current user`

```bash
> chown -R $USER:$USER .

# -R:		Do it recursively.
# .:		Do it for everything inside the current directory.
# $USER:	The user currently logged in.
```

> Create 'PDF' by merging images, text files and pdfs

```bash
# sudo apt install imagemagick

> convert image1.jpg image2.png text.txt PDFfile.pdf outputFileName.pdf
```

> Compress PDF files using ghostscript

```bash
> gs    -sDEVICE=pdfwrite           \
        -dCompatibilityLevel=1.4    \
        -dPDFSETTINGS=/ebook        \
        -dNOPAUSE                   \
        -dQUIET                     \
        -dBATCH                     \
        -sOutputFile=output.pdf     \
        input.pdf

# Additional options: http://milan.kupcevic.net/ghostscript-ps-pdf/
```