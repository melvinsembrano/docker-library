FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get install -y libopencv-dev libmicrohttpd-dev libjsoncpp-dev cmake git curl libcurl4-openssl-dev
RUN rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/Visu4link/pastec.git /pastec
RUN mkdir -p /pastec/build && mkdir /pastec/data
WORKDIR /pastec/build

RUN cmake ../ && make
RUN cd /pastec/data \
  && curl http://pastec.io/files/visualWordsORB.tar.gz -o visualWordsORB.tar.gz \
  && tar zxf visualWordsORB.tar.gz && rm visualWordsORB.tar.gz

EXPOSE 4212

CMD ./pastec -p 4212 /pastec/data/visualWordsORB.dat
