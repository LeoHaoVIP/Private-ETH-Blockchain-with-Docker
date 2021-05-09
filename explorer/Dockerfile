FROM node:6.11-alpine

WORKDIR /root

ARG gethnodeIP=""
ARG gethnodePort=""
ARG httpserverPort=8080

ADD ./ethereum-explorer ./ethereum-explorer

WORKDIR /root/ethereum-explorer

RUN apk add --update python make g++ git ca-certificates wget

RUN sed -i "s/geth_node_ip/$gethnodeIP/g" '/root/ethereum-explorer/app/app.js'
RUN sed -i "s/geth_node_port/$gethnodePort/g" '/root/ethereum-explorer/app/app.js'
RUN sed -i "s/http_server_port/$httpserverPort/g" '/root/ethereum-explorer/package.json'

RUN npm install -g bower
RUN npm install
RUN bower install

CMD npm start

EXPOSE 8080

