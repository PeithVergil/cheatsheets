ElasticSearch
=============

Installation
------------

Install Java runtime.

```sh
sudo add-apt-repository ppa:webupd8team/java

sudo apt-get update
sudo apt-get install openjdk-8-jdk
```

### Installing ElasticSearch v6.x.

```sh
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
```

```sh
sudo vim /etc/apt/sources.list.d/elastic-6.x.list
```

```sh
deb https://artifacts.elastic.co/packages/6.x/apt stable main
```

```sh
sudo apt-get update
sudo apt-get install elasticsearch
```

Update the ElasticSearch config file.

```sh
sudo vim /etc/elasticsearch/elasticsearch.yml
```

### Installing ElasticSearch v7.x.

```sh
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
```

```sh
sudo vim /etc/apt/sources.list.d/elastic-7.x.list
```

```sh
deb https://artifacts.elastic.co/packages/7.x/apt stable main
```

```sh
sudo apt-get update
sudo apt-get install elasticsearch
```

Update the ElasticSearch config file.

```sh
sudo vim /etc/elasticsearch/elasticsearch.yml
```

```sh
sudo service elasticsearch enable
sudo service elasticsearch start

# or
sudo systemctl start elasticsearch.service
sudo systemctl status elasticsearch.service
```

### Printing the logs.

```sh
# Tail the journal:
sudo journalctl -f

# List journal entries for elasticsearch:
sudo journalctl -u elasticsearch

# List journal entries for elasticsearch starting from a given time:
sudo journalctl --unit elasticsearch --since  "2016-10-30 18:17:16"
```

### Configure memory usage.

```sh
sudo vim /etc/elasticsearch/jvm.options
```

```
################################################################
## IMPORTANT: JVM heap size
################################################################
##
## You should always set the min and max JVM heap
## size to the same value. For example, to set
## the heap to 4 GB, set:
##
## -Xms4g
## -Xmx4g
##
## See https://www.elastic.co/guide/en/elasticsearch/reference/current/heap-size.html
## for more information
##
################################################################

# Xms represents the initial size of total heap space
# Xmx represents the maximum size of total heap space

-Xms256m
-Xmx256m
```