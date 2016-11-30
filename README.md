# HADOOP

### 1) Installation

```sh
$ cd /usr/local
$ wget http:/www.mirror.com/hadoop/common/hadoop-2.7.3.tar.gz
$ tar xzf hadoop-2.7.3.tar.gz
$ mv hadoop-2.7.3 hadoop
or 
$ ln -s hadoop-2.7.3/ hadoop

# make sure you have set the JAVA_HOME environment variable
echo $JAVA_HOME

# test hadoop installation
$ /usr/local/hadoop/bin/hadoop version

```
