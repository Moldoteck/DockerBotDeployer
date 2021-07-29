FROM node:14

WORKDIR /usr/

RUN git clone https://github.com/Moldoteck/AbstractExtractorBot

WORKDIR /usr/AbstractExtractorBot/

RUN yarn install
COPY .env .
COPY google_api.json .

CMD git pull && yarn install && yarn distribute
