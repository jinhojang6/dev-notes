## Remove all images

```
docker rmi --force $(docker images -a -q)
```


## Remove all containers including volumes

```
docker system prune --volumes
```

## Remove unused volumes

```
docker volume prune
```
