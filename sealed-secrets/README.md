```sh
export DOCKER_USERNAME=
export DOCKER_TOKEN=

echo -n bar | kubectl create secret generic docker-config --dry-run=client --from-literal="config.json={\"auths\": {\"https://index.docker.io/v1/\": {\"auth\": \"$(echo -n $DOCKER_USERNAME:$DOCKER_TOKEN|base64)\"}}}" -o json > docker-config.json

kubeseal <docker-config.json >docker-sealed-config.json
```