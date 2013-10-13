GCM Web Server (mavenized) 
==========================

Google Cloud Messaging (GCM) server side for Android.


Installation
------------

- Download the code

```xml
$ git clone https://github.com/huberflores/GCMServer.git
````

- Set the API key obtained in the Google API console in the ApiKeyInitializer.java file

```xml
$ mvn clean install
````

- Locate war file in the WebServer (e.g. Tomcat). The example shows how to do it for Amazon.

```xml
$ scp -i /home/huber/...KeyPath.../pk-huber_key.pem -r ./GCM-mavenized-server.war ubuntu@ec2-xx-xxx-x-x.compute-1.amazonaws.com:/home/ubuntu/
````

```xml
$ ssh -i /home/huber/...KeyPath.../pk-huber_key.pem ubuntu@ec2-xx-xxx-x-x.compute-1.amazonaws.com
````

```xml
$ mv GCM-mavenized-server.war /usr/local/tomcat/apache-tomcat-7.0.35/webapps/
````

```xml
/etc/init.d/tomcat start
````

Once online, you can register your device in the server. Registration happens to

```xml
http://ec2-xx-xxx-x-x.compute-1.amazonaws.com:8080/GCM-mavenized-server
````

FAQ
----

Since gcm-server.jar is not provided in a specific maven repository, a local maven repository that includes the library should be created. Alternatively, gcm-server repository can be establish using the following [link](https://github.com/slorber/gcm-server-repository)

```xml
$ mvn install:install-file -Dfile=/home/huber/.m2/repository/gcm-server-1.0.3.jar -DgroupId=com.google.android.gcm.server -DartifactId=gcm-server -Dversion=1.0.3 -Dpackaging=jar
````
```xml
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Maven Stub Project (No POM) 1
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-install-plugin:2.3:install-file (default-cli) @ standalone-pom ---
[INFO] Installing /home/huber/.m2/repository/gcm-server-1.0.3.jar to /home/huber/.m2/repository/com/google/android/gcm/server/gcm-server/1.0.3/gcm-server-1.0.3.jar
[INFO] Installing /tmp/mvninstall3661972569570313695.pom to /home/huber/.m2/repository/com/google/android/gcm/server/gcm-server/1.0.3/gcm-server-1.0.3.pom
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 0.610s
[INFO] Finished at: Sun Oct 13 17:23:12 EEST 2013
[INFO] Final Memory: 6M/118M
[INFO] ------------------------------------------------------------------------
````

Dependecy is defined in pom.xml as
```xml
<dependency>
    <groupId>com.google.android.gcm.server</groupId>
    <artifactId>gcm-server</artifactId>
    <version>1.0.3</version>
</dependency>
````





