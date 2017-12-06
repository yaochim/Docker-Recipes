FROM alpine:latest

LABEL Description="Funkykit base Alpine container with bash" Vendor="FlexStudios" authors="Kwok Yao Chim <yaochim8@gmail.com>"

RUN apk update && apk upgrade \
    && apk add --update bash \
    && rm -rf /var/cache/apk/* \

