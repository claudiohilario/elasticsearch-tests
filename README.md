# Elasticsearch Tests

## Install Elasticsearch (CentOS 7)

https://www.elastic.co/guide/en/elasticsearch/reference/current/rpm.html

```sh
rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
cd /etc/yum.repos.d
touch elasticsearch.repo
vi elasticsearch.repo
```
**elasticsearch.repo**
```
[elasticsearch]
name=Elasticsearch repository for 7.x packages
baseurl=https://artifacts.elastic.co/packages/7.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=0
autorefresh=1
type=rpm-md
```

```sh
sudo yum install --enablerepo=elasticsearch elasticsearch

sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable elasticsearch.service

sudo systemctl start elasticsearch.service
sudo systemctl stop elasticsearch.service
```
```sh
curl -X GET http://127.0.0.1:9200
```
https://stackoverflow.com/questions/58656747/elasticsearch-job-for-elasticsearch-service-failed

## Install Kibana (CentOS 7)
https://www.elastic.co/guide/en/kibana/current/rpm.html
```sh
rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
cd /etc/yum.repos.d
touch kibana.repo
vi kibana.repo
```
**kibana.repo**
```
[kibana-7.x]
name=Kibana repository for 7.x packages
baseurl=https://artifacts.elastic.co/packages/7.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=1
autorefresh=1
type=rpm-md
```

```sh
sudo yum install kibana

sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable kibana.service

sudo systemctl start kibana.service
sudo systemctl stop kibana.service
```


