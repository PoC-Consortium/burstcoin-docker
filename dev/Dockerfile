FROM maven:3-jdk-8-alpine

MAINTAINER PoC-Consortium

RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh && \
    git clone https://github.com/PoC-Consortium/burstcoin.git /etc/burstcoin

WORKDIR /etc/burstcoin

# compile
RUN ./burst.sh compile

# create volume mount points database
VOLUME ["/etc/burstcoin/burst_db"]

# expose ports
EXPOSE 6876 7123 8123 8125

# env
ENV BRS_DEVSTART "-Ddev=1"

# add config
ADD https://raw.githubusercontent.com/PoC-Consortium/burstcoin-docker/master/dev/brs.properties /etc/burstcoin/conf

# start
ENTRYPOINT ["./burst.sh"]
