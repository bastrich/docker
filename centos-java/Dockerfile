FROM centos:latest

RUN yum install java-1.8.0-openjdk -y \
    && yum install java-1.8.0-openjdk-devel -y \
    && echo "JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.232.b09-0.el8_0.x86_64" > /etc/profile.d/java.sh