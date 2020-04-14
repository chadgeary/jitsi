FROM ubuntu:18.04

RUN apt-get update && apt-get install -y coturn && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV TURN_PORT 3478
ENV TURN_PORT_START 30000
ENV TURN_PORT_END 39999
ENV TURN_SECRET {{ turn_secret.stdout }}
ENV TURN_REALM {{ my_domain }}
ENV TURN_SERVER_NAME {{ my_host }}

ADD coturn.sh coturn.sh
RUN chmod +x coturn.sh

CMD ["./coturn.sh"]
