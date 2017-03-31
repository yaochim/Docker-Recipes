FROM openjdk:8-jdk-alpine
LABEL Description="Docker image for basic Elasticsearch service, without XPack" Vendor="FlexStudios" Version="0.1" authors="Kwok Yao Chim <yaochim8@gmail.com>"
RUN apk add --update bash ca-certificates wget nodejs \
    && update-ca-certificates \
    && rm -rf /var/cache/apk/* \
    && adduser -s /bin/bash -u 6000 -D elasticsearch \
    && mkdir /opt \
    && wget -O /opt/elasticsearch-5.3.0.tar.gz https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.3.0.tar.gz \
    && tar -C /opt -xzf /opt/elasticsearch-5.3.0.tar.gz \
    && mv /opt/elasticsearch-5.3.0 /opt/elasticsearch \
    && mkdir /opt/elasticsearch/data /opt/elasticsearch/logs \
    && chown -R elasticsearch:elasticsearch /opt/elasticsearch
USER elasticsearch
EXPOSE 9200
CMD ["/opt/elasticsearch/bin/elasticsearch"]
