```
docker-compose up -d
```

Register runner containers
```
RUNNER_TOKEN=token-ABC
EXT_URL=http://192.168.33.10/
docker exec gitlab-runner \
       gitlab-runner register \
       -n \
       -r ${RUNNER_TOKEN} \
       --executor docker \
       --docker-image centos:latest \
       --url ${EXT_URL} \
       --clone-url http://192.168.33.10/ \
       --docker-volumes /var/run/docker.sock:/var/run/docker.sock \
       --docker-network-mode docker-compose_infraci_nw
```
