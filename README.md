# Liberty Installation

**Download required files**

    -   was_liberty
    -   unzip_6.0-21_amd64.deb
    -   InstallMgrLinux-1.8.7.1.zip
    -   ibm-java-sdk-8.0-5.15-linux-x64-installmgr.zip

> GO /home/user1/IBM/InstallationManager/eclipse/tools and run `./imcl -c`   
> P -> (Selecting Preferences will display the Java SDK repository to be installed).

![a](https://user-images.githubusercontent.com/3519706/59132215-40a54100-897d-11e9-8807-803be111cd64.png)

> 1  (select the repository you want to add.)    
> S  (To avoid searching for updates via the Internet, do the following without an “X”).    
> D (Select Add Repository and proceed to show the repository path to be added).

![a](https://user-images.githubusercontent.com/3519706/59132309-87933680-897d-11e9-8fe9-0828ee97f5f3.png)

>     /opt/javasdk8_05/repository.config (Repository path is given).
>     A (Apply Changes and Return to Preferences Menu).

![a](https://user-images.githubusercontent.com/3519706/59132357-a98cb900-897d-11e9-9f7b-aa037505596f.png)

> R (Return to Main Menu to return to the main menu).

![a](https://user-images.githubusercontent.com/3519706/59132395-bf9a7980-897d-11e9-99cc-14c258ac81b7.png)

>     1 (Enter 1 to proceed to Install).
>     1 (Select 1 to select which packages to install).
>     1 (Select 1 to install 8.0.5.15.)

![a](https://user-images.githubusercontent.com/3519706/59132426-d50fa380-897d-11e9-8715-354854dc9e97.png)

>    N  (N to continue the installation. The package is approved so  that).   
>    N  (N is written by confirming the package group and loading  location).

![a](https://user-images.githubusercontent.com/3519706/59132459-ea84cd80-897d-11e9-82d3-8d77f9856d86.png)

> I (If all directories and package group name are correct.)

![a](https://user-images.githubusercontent.com/3519706/59132489-fcff0700-897d-11e9-95be-4e3e66512365.png)

> F (When the installation is successful, F is completed.)

![a](https://user-images.githubusercontent.com/3519706/59132512-10aa6d80-897e-11e9-983a-b749adec4929.png)

> X (Selecting X exits Installation Manager.)
##### JVM CREATION PROCESS
To complete our Liberty installation, we need to create a JVM. Therefore:

> 1.  **cd /opt/IBM/WebSphere/AppServer/bin/**  go directory
> 2.  To create a JVM **./server create server1**  command is executed.
> 3.  To run the JVM **./server start server1**  command is executed.

![a](https://user-images.githubusercontent.com/3519706/59132546-29b31e80-897e-11e9-9fe6-5c5e6173c3d1.png)

I need to update the following line into server.xml.
/opt/IBM/WebSphere/AppServer/usr/servers/server1 directory and located in server.xml

**_To access this server from a remote client add a host attribute to the following element, e.g. host=""_** with **_Automatically expand WAR files and EAR files_**  
information is updated as follows.

**SERVER_IP should be your server IP.**

**Current state;**

![a](https://user-images.githubusercontent.com/3519706/59132574-3e8fb200-897e-11e9-8c8c-c4cad74928e3.png)

**<httpEndpoint host="*" httpPort="9080" httpsPort="9443" id="defaultHttpEndpoint">  
<httpOptions removeServerHeader="true" />  
<tcpOptions soReuseAddr="true" inactivityTimeout="60s"/>  
</httpEndpoint>**
**Last  State should be as follows;**

![a](https://user-images.githubusercontent.com/3519706/59132600-51a28200-897e-11e9-9bf1-d89a12627b92.png)










