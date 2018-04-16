# Installation Steps

## Install Orale JAVA 8
- $sudo add-apt-repository -y ppa:webupd8team/java
- $sudo apt-get update
- $sudo apt-get -y install oracle-java8-installer

## Install Elastic Search
- wget -qO - https://packages.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
- echo "deb http://packages.elastic.co/elasticsearch/2.x/debian stable main" | sudo tee -a /etc/apt/sources.list.d/elasticsearch-2.x.list
- sudo apt-get update
- sudo apt-get -y install elasticsearch
- sudo vi /etc/elasticsearch/elasticsearch.yml
      - uncomment #network.host: 0.0.0.0
- sudo service elasticsearch restart
- sudo update-rc.d elasticsearch defaults 95 10

## Refrences
- https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-elk-stack-on-ubuntu-14-04
