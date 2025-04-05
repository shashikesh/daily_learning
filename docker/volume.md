## Docker Volume
### 🧱 Two Types of Volume Mounts
1. `Docker Volumes` (Managed by Docker)
    Docker stores the data in /var/lib/docker/volumes/
    You don't need to know the exact path

2. `Bind Mounts` (External Mounts from Host)
You specify a host path to mount into the container
Useful for development or syncing with local files

#### bind Mount syntax
```shell
docker run -v /host/path:/container/path myimage
```
```
VOLUME ["/data"]
``` 
is doing like 
```bash
docker run -v /data myimage

```