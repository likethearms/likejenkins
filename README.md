# JENKINS DOCKER

## USEFUL PLUGINS
- Kubernetes Continuous Deploy Plugin
- Google Container Registry Auth Plugin
- Slack Notification Plugin
- Blue Ocean Plugin
- Global Slack Notifier Plugin
### Build
```sh
$ docker build -t likejenkins .
```
### Run 
```sh
$ docker run -d -p 8080:8080 -p 50000:50000 -v $(pwd)/jenkins_volume:/var/jenkins_home -v $(which docker):/usr/bin/docker -v /var/run/docker.sock:/var/run/docker.sock likejenkins
```
### Setup K8S registry
```sh
kubectl create secret docker-registry container-registry --docker-server='https://eu.gcr.io' --docker-username=_json_key --docker-password="$(cat google-service-key.json)" --docker-email=not.valid@email.com
```
### Maintenance 
Clear unused containers
```sh
0 4 * * * docker image prune -af
```
