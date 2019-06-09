## Liberty Service

    [Unit]
    Description=IBM WebSphere Liberty Server
    
    [Service]
    User=root
    Group=root
    ExecStart=/opt/IBM/WebSphere/Liberty/bin/server start member1
    ExecStop=/opt/IBM/WebSphere/Liberty/bin/server stop member1
    Environment=JAVA_HOME=/opt/IBM/WebSphere/Liberty/java/8.0
    PIDFile=/opt/IBM/WebSphere/Liberty/usr/servers/.pid/member1.pid
    Restart = always
    Type=forking
    TimeoutSec=600
    SuccessExitStatus=143 0
    
    [Install]
    WantedBy=multi-user.target
