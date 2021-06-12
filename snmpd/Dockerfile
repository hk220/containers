FROM quay.io/cybozu/ubuntu:20.04

LABEL org.opencontainers.image.source "https://github.com/hk220/containers"

WORKDIR /work

RUN apt-get update && \
    apt-get install -y snmpd snmp snmp-mibs-downloader && \
    rm -rf /var/lib/apt/lists/*

COPY snmpd.conf /etc/snmp/snmpd.conf

ENTRYPOINT [ "/usr/sbin/snmpd", "-f" ]

CMD [ "-Lo", "-C", "-c", "/etc/snmp/snmpd.conf" ]
