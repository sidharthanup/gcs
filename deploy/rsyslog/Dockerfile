FROM alpine:latest

LABEL maintainer="sanupkri@redhat.com"

ENV NAME="gluster-rsyslog" \
    DESC="Rsyslog for Gluster" \
    VERSION=0 \
    RELEASE=1 \
    ARCH=x86_64 \
    container=docker

RUN apk add --update rsyslog rsyslog-mmnormalize \
    && rm -rf /var/cache/apk/*

ADD rsyslog.conf /etc/rsyslog.conf
ADD gd2.rulebase /etc/rsyslog.d/gd2.rulebase

ENTRYPOINT ["rsyslogd", "-n"]
