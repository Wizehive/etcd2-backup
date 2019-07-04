# etcd2-backup

A simple backup utility for etcd v2

[![Build Status](https://travis-ci.org/evert0n/etcd2-backup.svg?branch=master)](https://travis-ci.org/evert0n/etcd2-backup)

## Install

```bash

npm install --global etcd2-backup
```

## Usage

```bash

  Usage: etcd2-backup [options] [command]


  Options:

    -V, --version                    output the version number
    -f, --file <file>                backup file
    -e, --etcd <etcd>                etcd url eg: https://host.docker.internal:4001
    -c, --concurrency <concurrency>  max parallel requests
    -h, --help                       output usage information


  Commands:

    restore   restore keys from backup file
    dump      dump keys to backup file
```

## Restoring a backup file

```bash
# Node
etcd2-backup -e https://host.docker.internal:4001 -f /backup/backup.json restore

# Docker
docker run -ti -v /my_backup_dir:/backup evert0n/etcd2-backup -e https://host.docker.internal:4001 -f /backup/backup.json restore
```

## Creating a backup file

```bash
# Node
etcd2-backup -e https://host.docker.internal:4001 -f /backup/backup.json dump

# Docker
docker run -ti -v /my_backup_dir:/backup evert0n/etcd2-backup -e https://host.docker.internal:4001 -f /backup/backup.json dump
```
