FROM artem236/rpi-alpine:3.6

RUN apk --no-cache add mosquitto=1.4.12-r0 && \
    mkdir -p /mosquitto/config /mosquitto/data /mosquitto/log && \
    cp /etc/mosquitto/mosquitto.conf /mosquitto/config

COPY docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["/usr/sbin/mosquitto", "-c", "/mosquitto/config/mosquitto.conf"]