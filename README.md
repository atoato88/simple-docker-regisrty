
# Docker registry with TLS and auth by docker_auth

At first, you must generate certs, read [README.md in certs folder](./certs/README.md)

Start containers:
```
docker-compose -f docker-compose.yaml up -d
```

You must set `insecure-registries` entry to /etc/docker/daemon.json  on docker client side, and restart it.

Example:
```
  .....
  "insecure-registries": ["192.168.1.20:5000"],
  .....
}
```

Login to docker-registry:
```
docker login https://<host-ip or domain-name>:5000
```

# Docker registry with non-TLS

Start containers:
```
docker-compose -f docker-compose-non-tls.yaml up -d
```

In this mode, you can connect with `localhost` only for docker-registry.

Login to docker-registry:
```
docker login http://localhost:5000
```
