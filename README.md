# jbossas7 

Dockerfile for JBoss AS 7.2 on Oracle Java SDK 7 and ubuntu.

JBoss AS .tar file is not provided.
Check for jboss-as-dist-7.2.0.Final.tar.gz  file on Internet, f.e. https://app.camunda.com/nexus/content/groups/public/org/jboss/as/jboss-as-dist/7.2.0.Final/

Build Oracle Java on ubuntu:

docker build -f dockerfile.java7 -t oracle/java7 .

Build with JBoss:

docker build -f dockerfile.jboss -t my/jbossas7 .

Run using mapped deployments and logs ( example for windows with  boot2docker):

docker run --rm   -v /c/Users/Public/deploy:/opt/jboss/jboss-as-7.2.0.Final/standalone/deployments -v /c/Users/Public/logs:/opt/jboss/jboss-as-7.2.0.Final/standalone/log -p 48080:8080 -p 49990:9990 my/jbossas7