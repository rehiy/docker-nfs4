# NFS v4 Server Container

[NFS v4](http://nfs.sourceforge.net/) server running under [s6 overlay](https://github.com/just-containers/s6-overlay) on [Alpine Linux](https://hub.docker.com/_/alpine/).

## Configuration

See [example directory](https://github.com/rehiy/docker-nfs4/tree/master/example) for sample config file.

## Quickstart

```
docker run --name nfs4 -d \
    --cap-add SYS_ADMIN \
    --publish 2049:2049 \
    --publish 2049:2049/udp \
    --volume /mnt/nfs-root:/nfs \
    --volume /mnt/share-1:/nfs/share-1 \
    --volume /mnt/share-2:/nfs/share-2 \
    --volume ./exports.txt:/etc/exports \
    vmlu/nfs4
```

### Mounting

```shell
mount.nfs4 localhost:/share-1 /tmp/nfs
```
