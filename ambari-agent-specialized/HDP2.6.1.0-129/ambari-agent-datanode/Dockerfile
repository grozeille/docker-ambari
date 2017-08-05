FROM grozeille/ambari-agent:2.5.1.0-v2

ADD http://public-repo-1.hortonworks.com/HDP/centos7/2.x/updates/2.6.1.0/hdp.repo /etc/yum.repos.d/HDP.repo

RUN yum install -y \
ambari-metrics-hadoop-sink \
ambari-metrics-monitor \
atlas-metadata-hive-plugin \
bigtop-jsvc \
datafu \
hadoop \
hadoop-client \
hadoop-hdfs \
hadoop-libhdfs \
hadoop-mapreduce \
hadoop-yarn \
hdp-select \
hive2 \
hive2-jdbc \
hive \
hive-hcatalog \
hive-jdbc \
hive-webhcat \
livy2 \
pig \
ranger-hdfs-plugin \
ranger-hive-plugin \
ranger-yarn-plugin \
slider \
smartsense-hst \
snappy \
snappy-devel \
spark2 \
spark2-python \
spark2-yarn-shuffle \
spark-yarn-shuffle \
storm-slider-client \
tez \
tez_hive2 \
zookeeper \
zookeeper-server \
&& yum clean all