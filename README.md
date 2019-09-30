### Simple load balancer
Simple project to practice NGINX load balancer settings. Use Docker Compose to start a testing environment.

Run a testing environment:  
```
cd simple-load-balancer

# Start the load balancer and the backend servers.
docker-compose up

# Docker Compose created a network named `simple-load-balancer_default` for us.
docker network ls

# Inspect the network and check the involved containers.
docker network inspect simple-load-balancer_default

# Hit the load balancer url many times and inspect docker logs. The log shows that requests have been evenly distributed to the backend servers.
curl 0.0.0.0:8080

# Stop the load balancer and the backend servers. Also remove the `simple-load-balancer_default` network.
docker-compose down -v
```

Reference:  
https://hub.docker.com/_/nginx  
https://upcloud.com/community/tutorials/configure-load-balancing-nginx/  
https://docker-curriculum.com/  
