You must set `insecure-registries` entry to /etc/docker/daemon.json  on docker client side, and restart it.

Example:
```
  .....
  "insecure-registries": ["192.168.1.20:5000"],
  .....
}
```
