## Liberty SSL Certificate Configuration

1.  Enable the SSL feature.
    
```xml
<featureManager>
...
<feature>ssl-1.0</feature>
...
</featureManager>
```
    
2.  Create an SSL configuration.
    
```xml
<ssl id="mySSLSettings" keyStoreRef="myKeyStore" />
<keyStore id="myKeyStore"
          location="server/server.p12"
          type="PKCS12"
          password="passServer12" />
```
    
3.  Configure your HTTP endpoint to use this SSL configuration or set the configuration as the default.
    
```xml
<sslDefault sslRef="mySSLSettings" />
```

**Example**
 ```xml   
<ssl id="mySSLSettings" keyStoreRef="defaultKeyStore" />
<keyStore id="defaultKeyStore" location="/opt/IBM/WebSphere/Liberty/usr/shared/resources/mycert.mydomain.p12" password="{aes}AFYIZMu5nT0" type="PKCS12"/>
<sslDefault sslRef="mySSLSettings" />
```
