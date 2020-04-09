## Liberty EndPoint

To access this server from a remote client add a host attribute to the following element, e.g. host="*" 

```xml
    <httpEndpoint host="*" httpPort="8080" httpsPort="9443" id="defaultHttpEndpoint">
    <httpOptions removeServerHeader="true" />
    <tcpOptions soReuseAddr="true" inactivityTimeout="60s" addressExcludeList="10.11.12.13" />
    </httpEndpoint>
```
