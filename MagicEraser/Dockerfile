FROM node:16

WORKDIR /usr/

RUN git clone https://github.com/Moldoteck/MagicEraser

WORKDIR /usr/MagicEraser/

RUN export DEBIAN_FRONTEND=noninteractive
RUN apt update
RUN apt install git-lfs -y
RUN git lfs install

RUN apt install -y apt-utils
RUN apt update

RUN git clone https://github.com/Moldoteck/lama
WORKDIR /usr/MagicEraser/lama

RUN git pull
RUN apt install -y python3-pip
RUN python3 -m pip install --upgrade pip
RUN pip3 install -r requirements.txt

WORKDIR /usr/MagicEraser/

RUN export PYTHONPATH="/usr/MagicEraser/lama:/usr/MagicEraser/lama/saicinpainting"
RUN yarn install
COPY .env .

CMD export PYTHONPATH="/usr/MagicEraser/lama:/usr/MagicEraser/lama/saicinpainting" && git pull && yarn install && yarn distribute
