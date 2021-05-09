FROM ethereum/client-go:alltools-v1.9.21

WORKDIR /root

EXPOSE 30301/udp
EXPOSE 30303/udp
EXPOSE 30301/tcp
EXPOSE 30303/tcp

ENV nodekeyhex ""
ENV bootnodeIP ""

CMD exec bootnode -nodekeyhex $nodekeyhex -addr $bootnodeIP:30301