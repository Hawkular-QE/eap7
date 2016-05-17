# What is this Docker image project?
Wildfly application server with built-in Hawkular monitoring agent
* [EAP7 Docker image]() 
* [Hawkular agent](https://github.com/hawkular/hawkular-agent)

# Example usage

```
docker run -d  -e HAWKULAR_SERVER=http://livingontheedge.hawkular.org hawkular/eap7-monitoring-agent
```
