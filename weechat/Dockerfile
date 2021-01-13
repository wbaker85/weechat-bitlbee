FROM alpine:latest
RUN apk update && apk upgrade && apk add weechat
RUN adduser -u 1000 -S -h /config weechat

USER weechat

ENTRYPOINT weechat-headless -r "/set relay.network.password ${relay_password}" -r "/relay add weechat 9001" -r "/server del bitlbee" -r "/server add bitlbee bitlbee/6667" -r "/connect bitlbee"