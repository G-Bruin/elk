# docker集成elk6.5.0版本以及x-pack破解
## 简介
- ELK 不是一款软件，而是 Elasticsearch、Logstash 和 Kibana 三种软件产品的首字母缩写。这三者都是开源软件，通常配合使用，而且又先后归于 Elastic.co 公司名下，所以被简称为 ELK Stack。ELK Stack 已经成为目前最流行的集中式日志解决方案
- Elasticsearch：分布式搜索和分析引擎，具有高可伸缩、高可靠和易管理等特点。基于 Apache Lucene 构建，能对大容量的数据进行接近实时的存储、搜索和分析操作。通常被用作某些应用的基础搜索引擎，使其具有复杂的搜索功能；
- Logstash：数据收集引擎。它支持动态的从各种数据源搜集数据，并对数据进行过滤、分析、丰富、统一格式等操作，然后存储到用户指定的位置；
- Kibana：数据分析和可视化平台。通常与 Elasticsearch 配合使用，对其中数据进行搜索、分析和以统计图表的方式展示；
## 使用说明
- 构建elastic中文分词版镜像
```
cd elastic
docker build -t gbruin/elastic:latest .
```
- 修改docker-compose.yml
```
xpack.security.enabled=false
docker-compose up -f docker-compose.yml  //启动容器
```
- 更新license
```
浏览器打开 http://127.0.0.1:5601，更新license
elastic/x-pack/yu-xiaolong-d46f3528-2446-4d18-99ea-085fe1e285dd-v5.json
```
![图片](https://github.com/lanqb-tech/elk/blob/master/images/WeChat23052aea4eef98f15e470aee438fcaf6.png)

- 最后修改docker-compose.yml
```
xpack.security.enabled=true
docker-compose up -f docker-compose.yml  //启动容器 本地搭建完成
```

- 注：本地我的docker配置memory3.5g，swap1.5g，不然内存不够

## 参考文章
- [加密Elasticsearch Docker Containeredit中的通信](https://www.elastic.co/guide/en/elasticsearch/reference/6.5/configuring-tls-docker.html#configuring-tls-docker)
- [x-pack破解](https://www.cnblogs.com/qilvfei/p/9956932.html)