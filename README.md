# JENKINS DOCKER

## USEFUL PLUGINS
- Kubernetes Continuous Deploy Plugin
- Google Container Registry Auth Plugin

```sh
$ docker run -d -p 8080:8080 -p 50000:50000 -v ./jenkins_volume:/var/jenkins_home -v $(which docker):/usr/bin/docker -v /var/run/docker.sock:/var/run/docker.sock TAG
```
