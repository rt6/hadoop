# HADOOP

### 1) Installation (Single Node)

```sh
$ cd /usr/local
$ wget http:/www.mirror.com/hadoop/common/hadoop-2.7.3.tar.gz
$ tar xzf hadoop-2.7.3.tar.gz
$ mv hadoop-2.7.3 hadoop
# or 
$ ln -s hadoop-2.7.3/ hadoop

# check JAVA_HOME environment variable
$ echo $JAVA_HOME

# add HADOOP_HOME and JAVA_HOME to bashrc
export HADOOP_HOME=/usr/local/hadoop
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

# find java home directory
$ readlink -f /usr/bin/java | sed "s:bin/java::"

# test hadoop installation
$ /usr/local/hadoop/bin/hadoop version

# test wordcount using mapreduce algorithm
$ mkdir ~/wordcount_input
$ cp /usr/local/hadoop/*.txt ~/wordcount_input
$ /usr/local/hadoop/bin/hadoop jar /usr/local/hadoop/share/hadoop/mapreduce/hadoop-mapreuce-examples-2.7.3.jar  wordcount wordcount_input/ wordcount_outpout

# see hadoop wordcount results
$ cat ~/wordcount_output/*

```

### 2) Installation (Pseudo Distributed Mode)
```sh
# add these to .bashrc
export HADOOP_HOME=/usr/local/hadoop 
export HADOOP_MAPRED_HOME=$HADOOP_HOME 
export HADOOP_COMMON_HOME=$HADOOP_HOME 
export HADOOP_HDFS_HOME=$HADOOP_HOME 
export YARN_HOME=$HADOOP_HOME 
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native 
export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin 
export HADOOP_INSTALL=$HADOOP_HOME 
export HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop
export HADOOP_OPTS="$HADOOP_OPTS -Djava.library.path=/usr/local/hadoop/lib/native"

# add JAVA_HOME to hadoop/etc/hadoop/hadoop-env.sh
export JAVA_HOME=/same/value/as/$JAVA_HOME

# add configs to these files
1. hadoop/etc/hadoop/core-site.xml   (make sure there is no space in the xml tag values)
1. hadoop/etc/hadoop/hdfs-site.xml
1. hadoop/etc/hadoop/yarn-site.xml
1. hadoop/etc/hadoop/mapred-site.xml

# check namenode configs for hdfs
$ bin/hdfs getconf -namenodes

# format hdfs namenode
$ bin/hdfs namenode -format

# start hdfs
$ start-dfs.sh

# start yarn
$ start-yarn.sh

# these 2 have been deprecated
$ stop-all.sh
$ start-all.sh

# see hdfs status in browser
http://localhost:50070/

# see yarn (all running jobs) in browser
http://localhost:8088/

```
