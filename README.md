## OpenShift Tomcat 7 Cartridge WebSockets Demo ##

OpenShift supports creating Apache Tomcat 7 applications. To create a tomcat-7 application , execute the command shown below.

```
rhc app create wsdemo tomcat-7
```

Remove the default source code generated by OpenShift

```
$ cd wsdemo
$ git rm -rf src/ pom.xml
$ git commit -am "removed default source"
```

Download Apache Tomcat 7 and unzip it. Apache Tomcat 7 comes bundle with WebSocket examples. Copy the examples folder under webapps directory to your OpenShift application webapps folder.

Add the source code and push to OpenShift

```
$ git add .
$ git commit -am "added tomcat7 examples"
$ git push
```

After git push successfully finishes , open the web browser and go to http://wsdemo-{domain-name}.rhcloud.com:8000/examples/websocket/. You will see list of WebSocket demos. Please note that to try websockets you have to use either 8000(http) or 8443(https) port.