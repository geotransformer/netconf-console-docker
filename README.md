# netconf-console docker image
This is a multi-stage Dockerfile that packages the [`netconf-console`](https://pypi.org/project/netconf-console/) tool in an Alpine based docker image running with python3.7.

Details and instructions are provided in this [blog post](https://netdevops.me/2020/netconf-console-in-a-docker-container/).

## Build
```bash
# considering 2.3.0 is the intended version
docker build -t hellt/netconf-console:2.3.0 .
docker push hellt/netconf-console:2.3.0
docker tag hellt/netconf-console:2.3.0 hellt/netconf-console:latest
docker push hellt/netconf-console:latest
```

## Deploy
```bash
# pull image
docker pull hellt/netconf-console

# verify that the tool is properly working,
docker run --rm -it hellt/netconf-console --help

# interactive console mode
admin@ubuntu:~$ docker run -it --rm hellt/netconf-console --host=xx.xxx.xxx.xxx --port=830 -u admin -p Admin@123
netconf> hello
<?xml version='1.0' encoding='UTF-8'?>
<nc:hello xmlns:nc="urn:ietf:params:xml:ns:netconf:base:1.0">
  <nc:capabilities>
  
# interactive shell mode

```
