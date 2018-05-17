FROM python:3.6.5-alpine3.7

LABEL Description="FlexStudios base Alpine3.7+Python3.6.5 container with bash" Vendor="FlexStudios" authors="Kwok Yao Chim <yaochim8@gmail.com>" version="0.01"

RUN apk update && apk upgrade \
    && apk add --update bash \
    && rm -rf /var/cache/apk/*

COPY requirements.txt /
RUN pip install --no-cache-dir -r requirements.txt

WORKDIR /usr/src/app
