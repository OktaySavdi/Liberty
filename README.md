# Liberty Installation

**download required files**

    -   was_liberty
    -   unzip_6.0-21_amd64.deb
    -   InstallMgrLinux-1.8.7.1.zip
    -   ibm-java-sdk-8.0-5.15-linux-x64-installmgr.zip

GO /home/user1/IBM/InstallationManager/eclipse/tools and run `./imcl -c` 
 P -> (Selecting Preferences will display the Java SDK repository to be installed).![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559911272797.png)
     1  (select the repository you want to add.)
     S  (To avoid searching for updates via the Internet, do the following without an “X”).
     D (Select Add Repository and proceed to show the repository path to be added).![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559911356052.png)
    /opt/javasdk8_05/repository.config (Repository path is given).
    A (Apply Changes and Return to Preferences Menu).![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559911387009.png)
    R (Return to Main Menu to return to the main menu).![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559911433900.png)
    1 (Enter 1 to proceed to Install).
    1 (Select 1 to select which packages to install).
    1 (Select 1 to install 8.0.5.15.)
    ![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559911477504.png)
    
   N  (N to continue the installation. The package is approved so that).
   N  (N is written by confirming the package group and loading location).![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559911530551.png)
        
   I (If all directories and package group name are correct.)![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559911544384.png)
        
   F (When the installation is successful, F is completed.)![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559911563498.png)
  
  X (Selecting X exits Installation Manager.)

##### JVM CREATION PROCESS

To complete our Liberty installation, we need to create a JVM. Therefore:

1.  1.  1.  **cd /opt/IBM/WebSphere/AppServer/bin/**  go directory
        2.  To create a JVM **./server create server1**  command is executed.
        3.  To run the JVM **./server start server1**  command is executed.

![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559912004464.png)

I need to update the following line into server.xml.
/opt/IBM/WebSphere/AppServer/usr/servers/server1 directory and located in server.xml

**_To access this server from a remote client add a host attribute to the following element, e.g. host=""_** with **_Automatically expand WAR files and EAR files_**  information is updated as follows.

**SERVER_IP should be your server IP.**

Current state;

![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559912554374.png)

**<httpEndpoint host="*" httpPort="9080" httpsPort="9443" id="defaultHttpEndpoint">  
<httpOptions removeServerHeader="true" />  
<tcpOptions soReuseAddr="true" inactivityTimeout="60s"/>  
</httpEndpoint>**

Last  State should be as follows;
  ![](http://10.60.193.77:9080/uploads/images/gallery/2019-06/scaled-840-/image-1559912571743.png)
