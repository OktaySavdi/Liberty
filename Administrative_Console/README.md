## Liberty Administrator Console

server.xml

**Enable features** 

    <featureManager>
    <feature>adminCenter-1.0</feature>
    </featureManager>

**Define an Administrator and non-Administrator**

    <basicRegistry id="basic">
    <user name="admin" password="adminpwd" />
    <user name="nonadmin" password="nonadminpwd" />
    </basicRegistry>

 **Assign 'admin' to Administrator** 

    <administrator-role>
    <user>admin</user>
    </administrator-role>

    <keyStore id="defaultKeyStore" password="Liberty" />

**To access this server from a remote client add a host attribute to the following element, e.g. host="*"** 

    <httpEndpoint host="*" httpPort="9086" httpsPort="9447" id="defaultHttpEndpoint">
    <httpOptions removeServerHeader="true" />
    <tcpOptions soReuseAddr="true" inactivityTimeout="60s" />
    </httpEndpoint>

**Console Adress**

http://localhost:9080/adminCenter/