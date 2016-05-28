FROM bimgbily/centos-java:latest

RUN mkdir /opt/tomcat
RUN cd /opt/tomcat
RUN wget http://apache-mirror.rbc.ru/pub/apache/tomcat/tomcat-9/v9.0.0.M4/bin/apache-tomcat-9.0.0.M4.tar.gz
RUN tar zxf apache-tomcat-9.0.0.M4.tar.gz -C /opt/tomcat
RUN rm apache-tomcat-9.0.0.M4.tar.gz

CMD /opt/tomcat/apache-tomcat-9.0.0.M4/bin/catalina.sh run
EXPOSE 8080
