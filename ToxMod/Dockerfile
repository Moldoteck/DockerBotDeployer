FROM node:14

WORKDIR /usr/

RUN git clone https://github.com/Moldoteck/ToxMod

WORKDIR /usr/ToxMod/

RUN yarn install
COPY .env .

CMD git pull && yarn install && yarn distribute
