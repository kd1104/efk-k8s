# efk-k8s
setup elastic search and logstach on master of k8s cluster.


Install Elasticsearch Logstash
1. Install java 8
add-apt-repository -y ppa:webupd8team/java
apt-get update
apt-get -y install oracle-java8-installer

2. Install Elasticsearch
1. wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
2. apt-get install apt-transport-https
3. echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-6.x.list
4. apt-get update
5. apt-get -y install elasticsearch
6.Edit in  /etc/elasticsearch/elasticsearch.yml
    - path.data: /var/lib/elasticsearch
    - path.logs: /var/log/elasticsearch
    - network.host: localhost (localhost change to ip or 0.0.0.0)
7. service elasticsearch restart


Install logstash
1. wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
2. sudo apt-get install apt-transport-https
3. echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-6.x.list
4.  apt-get update && sudo apt-get install logstash
5. cd /etc/logstash/conf.d/ --- check repo for conf.d files
6. Edit file /etc/logstash/logstash.yml
    - uncomment line path.config: /etc/logstash/conf.d/*.conf
    - path.data: /var/lib/logstash
    - path.logs: /var/log/logstash
 7. Service logstash restart
 
 
 
  
