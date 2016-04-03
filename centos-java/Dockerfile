FROM centos:latest

RUN yum install -y wget
RUN wget http://javadl.oracle.com/webapps/download/AutoDL?BundleId=207220
RUN mv AutoDL?BundleId=207220 jre-8u77-linux-x64.rpm
RUN rpm -ivh jre-8u77-linux-x64.rpm
RUN rm jre-8u77-linux-x64.rpm