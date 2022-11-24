---
title: "Redis"
tags: ""
---

# Redis

## Windows wsl
https://www.youtube.com/watch?v=1psWME8UH_0

Install the latest version of Redis on Windows 10 using the Windows Subsystem for Linux (WSL).

For your copying and pasting convenience, here are the installation commands:

```bash
$ sudo apt-add-repository ppa:redislabs/redis
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install redis-server
```

Once installed, you can start, stop, and restart the server:

```bash
$ sudo service redis-server start
$ sudo service redis-server stop
$ sudo service redis-server restart
```

NOTE: If you have trouble with the command to start the server, you might need to turn daemonization on in your redis.conf. To do that, open up /etc/redis/redis.conf and replace where it says "daemonize no" with "daemonize yes".


Install 
```bash
sudo apt-get install redis-server
```

```bash

redis-cli # Redis client

sudo service redis-server start
sudo service redis-server stop
sudo service redis-server restart

```
