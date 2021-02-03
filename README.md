# dod-sandbox
The sample application can be used to testing the JIB maven plugin.

Here parent pom.xml is configured for the JIB plugin.  
 
 Tested the app by moving the plugin to server module. The image is not getting created after adding the below changes in pom.xml, but not able to run it.
 
 ```
          <executions>
              <execution>
                <phase>package</phase>
                <goals>
                  <goal>dockerBuild</goal>
                </goals>
              </execution>
```

# With docker image

Command to build the docker image
$ devon mvn package jib:dockerBuild

 To run the docker image: 
$ docker run --publish 8081:8081 <image_name or image_id>

# Without docker image:

$devon mvn compile jib:build    -Djib.to.image=docker.io/<username>/<appname>:<tag>     -Djib.to.auth.username=<username>     -Djib.to.auth.password=<password>
   - this command uploads the image to the docker repository.
  
$ docker run --publish 8081:8081 <image_name or image_id>
