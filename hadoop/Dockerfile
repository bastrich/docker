FROM bimgbily/centos-java:latest

RUN yum install -y tmux
# RUN echo 0 | tee /proc/sys/kernel/yama/ptrace_scope

ENV HADOOP_DOWNLOAD_LINK http://apache-mirror.rbc.ru/pub/apache/hadoop/common/hadoop-3.2.1/hadoop-3.2.1.tar.gz
RUN wget $HADOOP_DOWNLOAD_LINK
ENV HADOOP_ARCHIVE_NAME hadoop-3.2.1.tar.gz
ENV HADOOP_HOME /opt/hadoop
ENV HADOOP_MAPRED_HOME /opt/hadoop

ENV HIVE_ARCHIVE_NAME apache-hive-3.1.3-bastrich1-bin.tar.gz
ENV HIVE_HOME /opt/hive
COPY $HIVE_ARCHIVE_NAME $HIVE_ARCHIVE_NAME
# ENV HIVE_DOWNLOAD_LINK https://cloclo5.datacloudmail.ru/attach/7ZunbZvjwQuaRPrHrqGfe5TC6i2764Me2LLnY38J6kkG5kiudhFUodfFCk26x3xmuL9EdB/bastrich@bk.ru/hadoop/apache-hive-3.1.3-bastrich-bin.tar.gz
# RUN wget $HIVE_DOWNLOAD_LINK

ENV TEZ_ARCHIVE_NAME tez-0.10.1-bastrich.tar.gz
ENV TEZ_HOME /opt/tez
COPY $TEZ_ARCHIVE_NAME $TEZ_ARCHIVE_NAME
# ENV TEZ_DOWNLOAD_LINK https://cloclo5.datacloudmail.ru/attach/81iSxs8mNJMEqQqNYdVa2Su33rCDxDqmugrj7c64AYWGQXo1nY6mKnVEFTq1ogvkDAqKxT/bastrich@bk.ru/hadoop/tez-0.10.1-bastrich.tar.gz
# RUN wget $TEZ_DOWNLOAD_LINK

ENV SPARK_ARCHIVE_NAME spark-3.0.0-bastrich1-bin-custom-spark.tgz
ENV SPARK_HOME /opt/spark
COPY $SPARK_ARCHIVE_NAME $SPARK_ARCHIVE_NAME
# ENV SPARK_DOWNLOAD_LINK https://cloclo5.datacloudmail.ru/attach/81NqvQoXyiaREzDwfhW3ghMgScEXXdxhgy96bHku84TWgcCXonCErrC8E8vPzwM9PHAuQi/bastrich@bk.ru/hadoop/spark-3.0.0-SNAPSHOT-bin-custom-spark.tgz
# RUN wget $SPARK_DOWNLOAD_LINK

ENV SQOOP_ARCHIVE_NAME sqoop-bastrich.bin__hadoop-3.2.1.tar.gz
ENV SQOOP_HOME /opt/sqoop
COPY $SQOOP_ARCHIVE_NAME $SQOOP_ARCHIVE_NAME

ENV FLUME_ARCHIVE_NAME apache-flume-1.10.0-bastrich-bin.tar.gz
ENV FLUME_HOME /opt/flume
COPY $FLUME_ARCHIVE_NAME $FLUME_ARCHIVE_NAME

RUN mkdir $HADOOP_HOME \
      && tar -xvf $HADOOP_ARCHIVE_NAME -C $HADOOP_HOME --strip-components 1 \
      && rm -rf $HADOOP_ARCHIVE_NAME

RUN mkdir $HIVE_HOME \
      && tar -xvf $HIVE_ARCHIVE_NAME -C $HIVE_HOME --strip-components 1 \
      && rm -rf $HIVE_ARCHIVE_NAME
RUN wget -P /opt/hive/lib https://jdbc.postgresql.org/download/postgresql-42.2.8.jar

RUN mkdir $TEZ_HOME \
      && tar -xvf $TEZ_ARCHIVE_NAME -C $TEZ_HOME

RUN mkdir $SPARK_HOME \
      && tar -xvf $SPARK_ARCHIVE_NAME -C $SPARK_HOME --strip-components 1 \
      && rm -rf $SPARK_ARCHIVE_NAME

RUN mkdir $SQOOP_HOME \
      && tar -xvf $SQOOP_ARCHIVE_NAME -C $SQOOP_HOME --strip-components 1 \
      && rm -rf $SQOOP_ARCHIVE_NAME
RUN wget -P /opt/sqoop/lib https://jdbc.postgresql.org/download/postgresql-42.2.8.jar
RUN wget -P /opt/sqoop/lib https://repo1.maven.org/maven2/commons-lang/commons-lang/2.6/commons-lang-2.6.jar

RUN mkdir $FLUME_HOME \
      && tar -xvf $FLUME_ARCHIVE_NAME -C $FLUME_HOME --strip-components 1 \
      && rm -rf $FLUME_ARCHIVE_NAME

ENV PATH=${PATH}:/opt/hadoop/bin:/opt/hive/bin:/opt/spark/bin:/opt/sqoop/bin:/opt/flume/bin

ENV HADOOP_CONF_DIR=/etc/hadoop/conf
ENV HIVE_CONF_DIR=/etc/hive/conf
ENV TEZ_CONF_DIR=/etc/tez/conf
ENV SPARK_CONF_DIR=/etc/spark/conf
ENV FLUME_CONF_DIR=/etc/flume/conf

ENV TEZ_JARS=/opt/tez