FROM grozeille/ambari-agent:2.5.1.0-v2

ADD http://public-repo-1.hortonworks.com/HDP/centos7/2.x/updates/2.6.1.0/hdp.repo /etc/yum.repos.d/HDP.repo

RUN yum install -y \
ambari-metrics-hadoop-sink \
ambari-metrics-monitor \
hdp-select \
smartsense-hst \
zookeeper \
zookeeper-server \
&& yum clean all