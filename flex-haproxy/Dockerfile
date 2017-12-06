FROM alpine:latest

LABEL Description="Funkykit HAProxy container" Vendor="FlexStudios" authors="Kwok Yao Chim <yaochim8@gmail.com>"

RUN apk update && apk upgrade \
    && apk add --update bash haproxy haproxy-doc haproxy-systemd-wrapper \
    && rm -rf /var/cache/apk/* \
