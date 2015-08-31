# Jenkins SSH slave Docker image

[`jenkinsci/ssh-slave`](https://hub.docker.com/r/jenkinsci/ssh-slave/)

A [Jenkins](https://jenkins-ci.org) slave using SSH to establish connection.

See [Jenkins Distributed builds](https://wiki.jenkins-ci.org/display/JENKINS/Distributed+builds) for more info.

## Running with SSH

To run a Docker container

    docker run jenkinsci/ssh-slave "<public key>"

You'll then be able to connect this slave using ssh-slaves-plugin as "jenkins" with the matching private key.

## Running with plain docker

If you have a working docker client on Jenkins master, you can directly use it:

    docker run -i -u jenkins --rm jenkins-slave java -jar /usr/share/jenkins/slave.jar

In this mode, stdin and stout are directly connected to Jenkins. Note that build container will be destroyed upon Jenkins restart.

