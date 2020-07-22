## Remove all images

```
docker rmi --force $(docker images -a -q)
```

<br/>


## Remove all containers including volumes

```
docker system prune --volumes
```

<br/>

## Remove unused volumes

```
docker volume prune
```

<br/>

## Copy
Host >> Container
```
docker cp [host path] [container name]:[container path]
```

Container >> Host
```
docker cp [container name]:[container path] [host path]
```
