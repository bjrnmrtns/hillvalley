FROM alpine:3.16

RUN apk add --no-cache openrc influxdb

RUN mkdir -p /etc/influxdb /var/lib/influxdb && \
    chown influxdb:influxdb /etc/influxdb /var/lib/influxdb && \
    mkdir -p /run/openrc && \
    touch /run/openrc/softlevel

ENTRYPOINT ["sh", "-c", "rc-status; rc-service influxdb start; /bin/sh"]
