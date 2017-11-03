FROM alpine
ARG ES_VERSION=5.6.1
LABEL Description="Docker image for basic Kibana service, without XPack" Vendor="FlexStudios" Version="${ES_VERSION}" authors="Kwok Yao Chim <yaochim8@gmail.com>"
RUN apk add --update bash ca-certificates wget nodejs \
    && update-ca-certificates \
    && rm -rf /var/cache/apk/* \
    && adduser -s /bin/bash -u 6000 -D kibana \
    && mkdir /opt \
    && wget -O /opt/kibana-${ES_VERSION}-linux-x86_64.tar.gz https://artifacts.elastic.co/downloads/kibana/kibana-${ES_VERSION}-linux-x86_64.tar.gz \
    && tar -C /opt -xzf /opt/kibana-${ES_VERSION}-linux-x86_64.tar.gz \
    && mv /opt/kibana-${ES_VERSION}-linux-x86_64 /opt/kibana \
    && mv /opt/kibana/node/bin/node /opt/kibana/node/bin/node.orig \
    && chown -R kibana:kibana /opt/kibana
USER kibana
EXPOSE 5601
CMD ["/opt/kibana/bin/kibana"]
