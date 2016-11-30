# HADOOP

### 1) Installation

```sh
$ cd /usr/local
$ wget http:/www.mirror.com/hadoop/common/hadoop-2.7.3.tar.gz
$ tar xzf hadoop-2.7.3.tar.gz
$ mv hadoop-2.7.3 hadoop
# or 
$ ln -s hadoop-2.7.3/ hadoop

# check JAVA_HOME environment variable
$ echo $JAVA_HOME

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
