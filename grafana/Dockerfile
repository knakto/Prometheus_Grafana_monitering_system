FROM grafana/grafana-oss:latest

USER root

RUN apk add --no-cache openssl

RUN openssl req -x509 -newkey rsa:4096 \
    -keyout /etc/grafana/grafana.key \
    -out /etc/grafana/grafana.crt \
    -sha256 -days 365 -nodes \
    -subj '/CN=localhost'

RUN chown 472:472 -R /etc/grafana

USER 472
