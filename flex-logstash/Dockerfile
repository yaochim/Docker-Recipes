FROM openjdk:8-jdk-alpine
LABEL Description="Docker image for basic Logstash service" Vendor="FlexStudios" Version="5.6.1" authors="Kwok Yao Chim <yaochim8@gmail.com>"
ARG ES_VERSION=5.6.1
ENV TZONE="Europe/London" ES_VERSION="${ES_VERSION}" JAVA_HOME="/usr/lib/jvm/default-jvm"
RUN apk add --update bash ca-certificates wget tzdata \
    && update-ca-certificates \
    && rm -rf /var/cache/apk/* \
    && echo "${TZONE}" > /etc/timezone \
    && ln -sf /usr/share/zoneinfo/${TZONE} /etc/localtime \
    && adduser -s /bin/bash -u 6000 -D logstash \
    && mkdir /opt \
    && wget -O /opt/logstash-${ES_VERSION}.tar.gz https://artifacts.elastic.co/downloads/logstash/logstash-${ES_VERSION}.tar.gz \
    && tar -C /opt -xzf /opt/logstash-${ES_VERSION}.tar.gz \
    && mv /opt/logstash-${ES_VERSION} /opt/logstash \
    && mkdir /opt/logstash/conf.d /opt/logstash/logs \
    && chown -R logstash:logstash /opt/logstash
USER logstash
EXPOSE 5044
ENV JAVA_HOME /usr/lib/jvm/default-jvm
WORKDIR /opt/logstash
ENTRYPOINT ["/opt/logstash/bin/logstash"]
CMD ["-f","/opt/logstash/conf.d/"]

