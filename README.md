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
scp -i /home/huber/...KeyPath.../pk-huber_key.pem -r ./GCM-mavenized-server.war ubuntu@ec2-xx-xxx-x-x.compute-1.amazonaws.com:/home/ubuntu/
````

```xml
ssh -i /home/huber/...KeyPath.../pk-huber_key.pem ubuntu@ec2-xx-xxx-x-x.compute-1.amazonaws.com
````

```xml
mv GCM-mavenized-server.war /usr/local/tomcat/apache-tomcat-7.0.35/webapps/
````

```xml
/etc/init.d/tomcat start
````

Once online, you can register you device to the server. Registration happens to

```xml
http://ec2-xx-xxx-x-x.compute-1.amazonaws.com:8080/GCM-mavenized-server
````



