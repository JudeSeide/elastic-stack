FROM docker.elastic.co/beats/heartbeat:7.3.1

COPY ./config/heartbeat.yml /usr/share/heartbeat/heartbeat.yml
USER root

RUN chown root:heartbeat /usr/share/heartbeat/heartbeat.yml
RUN chmod go-w /usr/share/heartbeat/heartbeat.yml

USER heartbeat
