FROM python:3.6-alpine3.7

LABEL Description="Harbour Master for controlling containers on Docker hosts" Vendor="FlexStudios" authors="Kwok Yao Chim <yaochim8@gmail.com>"

RUN apk update \
	&& apk upgrade \
    && apk add --update bash \
    curl \
    ca-certificates \
    && rm -rf /var/cache/apk/* \

