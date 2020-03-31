if you see the error below

    "The driver could not establish a secure connection to SQL Server by using Secure Sockets Layer (SSL) encryption. Error: "SQL Server did not return a response. The connection has been closed"

create `jvm.options` file and add the following parameters

    -Dcom.ibm.jsse2.overrideDefaultTLS=true
    -Dcom.ibm.jsse2.overrideDefaultProtocol=TLSv12
