FROM python:3.6-alpine

LABEL Description="FlexStudios base Alpine and Python3.6 container with bash" Vendor="FlexStudios" authors="Kwok Yao Chim <yaochim8@gmail.com>" version="0.02"

RUN apk update && apk upgrade \
    && apk add --update bash curl gcc musl-dev python3-dev libffi-dev \
    && rm -rf /var/cache/apk/*

COPY requirements.txt /
RUN pip3 install --no-cache-dir -r requirements.txt

WORKDIR /usr/src/app
