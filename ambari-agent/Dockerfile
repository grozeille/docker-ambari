FROM grozeille/ambari-base:7.2-v8
MAINTAINER Hortonworks

# add ambari repo
ADD ambari.repo /etc/yum.repos.d/

RUN yum install -y  ambari-agent && yum clean all
#RUN find /etc/rc.d/rc* -name "*ambari-agent" | xargs rm -v

# add a custom folder to the hadoop classpath
RUN mkdir -p /usr/lib/hadoop/lib
ENV HADOOP_CLASSPATH /data/jars/*:/usr/lib/hadoop/lib/*

ADD public-hostname.sh /etc/ambari-agent/conf/public-hostname.sh
ADD internal-hostname.sh /etc/ambari-agent/conf/internal-hostname.sh
RUN sed -i "/\[agent\]/ a public_hostname_script=\/etc\/ambari-agent\/conf\/public-hostname.sh" /etc/ambari-agent/conf/ambari-agent.ini
RUN sed -i "/\[agent\]/ a hostname_script=\/etc\/ambari-agent\/conf\/internal-hostname.sh" /etc/ambari-agent/conf/ambari-agent.ini

# do not use the docker0 interface
RUN sed -i "s/\"ifconfig\"/\"ifconfig eth0\"/" /usr/lib/python2.6/site-packages/ambari_agent/Facter.py

# Add jars from packer image
ADD dash-azure-storage-2.2.0.jar /usr/lib/hadoop/lib/
ADD gcs-connector-latest-hadoop2.jar /usr/lib/hadoop/lib/

ADD init/init-agent.sh /opt/ambari-agent/init-agent.sh
RUN chmod u+x /opt/ambari-agent/init-agent.sh

ADD init/ambari-agent.service /etc/systemd/system/ambari-agent.service

RUN systemctl enable ambari-agent

RUN echo DefaultEnvironment=\"JAVA_HOME=$JAVA_HOME\" \"HADOOP_CLASSPATH=$HADOOP_CLASSPATH\" >> /etc/systemd/system.conf

RUN groupadd -g 1000 hadoop && \
groupadd -g 1001 hdfs && \
groupadd -g 1002 zookeeper && \
groupadd -g 1003 yarn && \
groupadd -g 1004 mapred && \
groupadd -g 1005 livy && \
groupadd -g 1006 spark && \
useradd -u 1001 -g 1000 -G hadoop,hdfs hdfs && \
useradd -u 1002 -g 1000 -G hadoop zookeeper && \
useradd -u 1003 -g 1000 -G hadoop yarn && \
useradd -u 1004 -g 1000 -G hadoop mapred && \
useradd -u 1005 -g 1000 -G hadoop livy && \
useradd -u 1006 -g 1000 -G hadoop spark && \
useradd -u 1007 -g 1000 -G hadoop hive && \
useradd -u 1008 -g 1000 -G hadoop hcat && \
useradd -u 1009 -g 1000 -G hadoop,users tez && \
useradd -u 1010 -g 1000 -G hadoop ams && \
useradd -u 1011 -g 1000 -G hadoop,users ambari-qa && \
useradd -u 1012 -g 1000 -G hadoop,hdfs activity_analyzer
