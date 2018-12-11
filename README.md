# dev_kafka
Kafka Development

- - -
Install The Following:
## JAVA 8
https://download.oracle.com/otn-pub/java/jdk/8u191-b12/2787e4a523244c269598db4e85c51e0c/jdk-8u191-linux-x64.tar.gz

## Zookeeper
https://zookeeper.apache.org/releases.html#download
https://www.apache.org/dyn/closer.cgi/zookeeper/

### Standalone Server Instructions using 3.4.13 (http://apache.mirrors.lucidnetworks.net/zookeeper/zookeeper-3.4.13/zookeeper-3.4.13.tar.gz)
# tar -xvf zookeeper-3.4.13.tar.gz
# mv zookeeper-3.4.13 /usr/local/zookeeper
# mkdir -p /var/lib/zookeeper
# cat > /usr/local/zookeeper/conf/zoo.cfg << EOF
> tickTime=2000
> dataDir=/var/lib/zookeeper
> clientPort=2181
> EOF
# export JAVA_HOME=/usr/java/jdk1.8.0_191
# /usr/local/zookeeper/bin/zkServer.sh start

JMX enabled by default
Using config: /usr/local/zookeeper/bin/../conf/zoo.cfg
Starting zookeeper ... STARTED
#

## SCALA (2.11.x/2.12.x)
https://www.scala-lang.org/download/
### SBT
https://piccolo.link/sbt-1.2.7.tgz

## SCALA (2.12.x)
https://downloads.lightbend.com/scala/2.12.8/scala-2.12.8.tgz
