FROM openjdk:8-jdk-alpine

MAINTAINER PoC-Consortium

# copy all files from cloned repository
COPY . /etc/burstcoin

# create volume mount points for config and database
VOLUME ["/etc/burstcoin/conf", "/etc/burstcoin/burst_db"]

# expose burstcoin ports
EXPOSE 8125 8123

# start
ENTRYPOINT ["java", "-classpath", "/etc/burstcoin/burst.jar:/etc/burstcoin/conf", "nxt.Nxt"]
