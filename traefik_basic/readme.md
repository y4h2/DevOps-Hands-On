# Test Traefik Basic Functionalities
- reverse proxy
- load balancer

# Command
test reverse proxys
```
docker-compose up -d
curl -H Host:whoami.docker.localhost http://127.0.0.1:8888
```

test load balancer
```
docker-compose up -d --scale whoami=2
curl -H Host:whoami.docker.localhost http://127.0.0.1:8888
```