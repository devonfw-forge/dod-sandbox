# dod-sandbox
A sandbox to play around with .github templates for PRs enforcing DoD, etc.

=== With docker image

Command to build the docker image

$ devon mvn package jib:dockerBuild

Run the docker image:

$ docker run --publish 8081:8081 <image_name or image_id>

=== Without docker image:

$devon mvn compile jib:build    -Djib.to.image=docker.io/<username>/<appname>:<tag>     -Djib.to.auth.username=<username>     -Djib.to.auth.password=<password>
   - this command uploads the image to the docker repository.
  
$ docker run --publish 8081:8081 <image_name or image_id>
