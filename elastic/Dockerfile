FROM docker.elastic.co/elasticsearch/elasticsearch:6.5.0

#RUN yes | /usr/share/elasticsearch/bin/elasticsearch-plugin install https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v6.5.0/elasticsearch-analysis-ik-6.5.0.zip

COPY x-pack/x-pack-core-6.5.0.jar /usr/share/elasticsearch/modules/x-pack-core/x-pack-core-6.5.0.jar

RUN yes | /usr/share/elasticsearch/bin/elasticsearch-plugin install https://assets-cdn.lanqb.com/elasticsearch-analysis-ik-6.5.0.zip


#COPY config/elasticsearch.yml /usr/share/elasticsearch/config/elasticsearch.yml

#RUN chown elasticsearch:elasticsearch /usr/share/elasticsearch/data