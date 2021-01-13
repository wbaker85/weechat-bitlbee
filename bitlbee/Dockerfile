FROM alpine:latest
RUN apk update && apk upgrade && apk add bitlbee
RUN adduser -u 1000 -S -h /var/lib/bitlbee bitlbee
RUN touch /var/run/bitlbee.pid && chown bitlbee:nogroup /var/run/bitlbee.pid

COPY bitlbee.conf /etc/bitlbee/bitlbee.conf

USER bitlbee
VOLUME ["/var/lib/bitlbee"]
ENTRYPOINT ["/usr/sbin/bitlbee", "-n", "-v"]