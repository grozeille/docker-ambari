FROM grozeille/ambari-agent:2.5.1.0-v2

ADD http://public-repo-1.hortonworks.com/HDP/centos7/2.x/updates/2.6.1.0/hdp.repo /etc/yum.repos.d/HDP.repo

RUN yum install -y \
ambari-metrics-hadoop-sink \
ambari-metrics-monitor \
bigtop-jsvc \
hadoop \
hadoop-client \
hadoop-hdfs \
hadoop-libhdfs \
hadoop-mapreduce \
hadoop-yarn \
hdp-select \
livy2 \
ranger-hdfs-plugin \
ranger-yarn-plugin \
smartsense-hst \
snappy \
snappy-devel \
spark2 \
spark2-python \
spark2-yarn-shuffle \
spark-yarn-shuffle \
zookeeper \
&& yum clean all