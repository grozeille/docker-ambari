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
pig \
ranger-hdfs-plugin \
ranger-hive-plugin \
ranger-yarn-plugin \
smartsense-hst \
snappy \
snappy-devel \
spark2-yarn-shuffle \
spark-yarn-shuffle \
tez \
tez_hive2 \
zookeeper \
zookeeper-server \
net-tools \
&& yum clean all