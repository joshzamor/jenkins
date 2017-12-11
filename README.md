# Personal Jenkins server scripts

## docker compose

Jenkins, as well as a reverse proxy, are ran in Docker and may be started/stopped with the `docker-compose.yml`
file.

To start:

```
docker-compose up -d
```

An important volume is the `jenkins_home` volume which should contain jenkins config/logs/workspace, etc.

### Manaual setup

- The first start you'll need to get the initial jenkins password.  Something akin to:  
  `docker run -it --rm -v jenkins_home:/var/jenkins_home alpine sh` should do.
- The agent connection to the rpi device needs to be setup.  This is via SSH with the private key from the rpi.
- Each pipeline below needs to be created, and the Jenkinsfile checked out from this repo.

## Pipelines

This directory contains a number of Jenkinsfiles with basic stages & steps for syncing.
