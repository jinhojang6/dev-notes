## ports
Expose ports
Either specify both ports `(HOST:CONTAINER)`, or just the container port (an ephemeral host port is chosen).

```
ports:
  - "3000"
  - "3000-3005"
  - "8000:8000"
  - "9090-9091:8080-8081"
  - "49100:22"
  - "127.0.0.1:8001:8001"
  - "127.0.0.1:5000-5010:5000-5010"
  - "6060:6060/udp"
  - "12400-12500:1240"
```

- [Reference](https://docs.docker.com/compose/compose-file/#ports)