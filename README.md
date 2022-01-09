# How-to-set-up-ELK-on-ubuntu
How to set up ELK on ubuntu


## Install elasticsearch 
```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get update 
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
echo "deb https://artifacts.elastic.co/packages/oss-7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
```

```
sudo apt-get update 
sudo apt-get install elasticsearch
```


```
sudo vim /etc/elasticsearch/elasticsearch.yml 

network.host: localhost 
http.port:9200
cluster.initial_master_nodes: ["<PrivateIP"]
```

test elasticsearch
```
sudo service elasticsearch status
curl localhost:9200
```

## Installing Logstash
install java
```
sudo apt-get install default-jre
```

```
java -version
```

```
sudo apt-get install logstash
```

## Installing Kibana
```
sudo apt-get install kibana
```

config kibana
```
vi /etc/kibana/kibana.yml
server.port: 5601 
elasticsearch.hosts: ["http://localhost:9200"]
```

start Kibana
```
sudo service kibana start
```

Open chrome and go to this url
```
http://localhost:5601
```


## Installing Beats
### Installing Beats
```
sudo apt-get install metricbeat
```

### start Metricbeat
```
sudo service metricbeat start
```

### check status beat
```
sudo service metricbeat status
```
