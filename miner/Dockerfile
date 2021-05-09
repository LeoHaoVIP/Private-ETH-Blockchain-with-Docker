FROM ethereum/client-go:alltools-v1.9.21

WORKDIR /root

ARG password
ARG privatekey
RUN echo $password > ~/.accountpassword
RUN echo $privatekey > ~/.privatekey
ADD ./genesis.json ./genesis.json
RUN geth init genesis.json
RUN geth account import --password ~/.accountpassword ~/.privatekey

EXPOSE 8545
EXPOSE 30303

ENV address ""
ENV bootnodeID ""
ENV bootnodeIP ""

CMD exec geth --bootnodes "enode://$bootnodeID@$bootnodeIP:30301" --networkid "19990415" --verbosity=4 --rpc --rpcaddr "0.0.0.0" --rpcapi "eth,web3,net,admin,debug,db,personal" --rpccorsdomain "*" --allow-insecure-unlock --syncmode="full" --mine --gasprice "0" --etherbase $address --unlock $address --password ~/.accountpassword
