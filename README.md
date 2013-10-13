GCM Web Server 
==============

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

Once online, you can register you device to the server.
