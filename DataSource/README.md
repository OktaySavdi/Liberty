## Liberty DataSource

**MSSQL DataSource**

[Other DB Link:](https://www.ibm.com/support/knowledgecenter/en/SS7K4U_liberty/com.ibm.websphere.wlp.zseries.doc/ae/twlp_dep_configuring_ds.html)
```xml
    <library id="MSJDBCLib">
    <file name="/opt/IBM/WebSphere/Liberty/SQLJDBC/sqljdbc.jar"/>
    </library>
    
    <dataSource id="mssqlJDBC" jndiName="jdbc/mssqlJDBC">
    <connectionManager purgePolicy="FailingConnectionOnly" numConnectionsPerThreadLocal="2" minPoolSize="5" maxPoolSize="50" connectionTimeout="10s" agedTimeout="30m"/>
    <jdbcDriver libraryRef="MSJDBCLib"/>
    <properties.microsoft.sqlserver user="unigw" databaseName="MyDB" serverName="10.13.14.15" portNumber="1433" password="{xor}MYPASSWORD"/>
    </dataSource>
```
**DB2 DataSource**
```xml
    <library id="db2lib">
    <fileset dir="/opt/IBM/WebSphere/AppServer/usr/shared/resources/db2" includes="db2jcc4.jar"/>
    <fileset dir="/opt/IBM/WebSphere/AppServer/usr/shared/resources/db2" includes="db2jcc_license_cu.jar"/>
    </library>
    
    <dataSource statementCacheSize="100" jndiName="jdbc/appl" isolationLevel="TRANSACTION_READ_COMMITTED" id="db2" connectionSharing="MatchCurrentState">
    <connectionManager purgePolicy="FailingConnectionOnly" numConnectionsPerThreadLocal="2" minPoolSize="5" maxPoolSize="50" connectionTimeout="10s" agedTimeout="30m"/>
    <jdbcDriver libraryRef="db2lib"/>
    <properties.db2.jcc user="MyUser" serverName="10.13.14.15" portNumber="50000" password="MYPASSWORD" databaseName="MyDB"/>
    </dataSource>
```
