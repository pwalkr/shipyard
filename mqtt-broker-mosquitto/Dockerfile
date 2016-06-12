FROM debian
RUN apt-get update

ENV MOSQUITTO_VERSION 1.4.9
RUN apt-get install --yes build-essential
RUN apt-get install --yes libssl-dev
RUN apt-get install --yes libc-ares-dev
RUN apt-get install --yes uuid-dev
RUN apt-get install --yes curl
RUN mkdir /mosquitto
WORKDIR /mosquitto
RUN curl "http://mosquitto.org/files/source/mosquitto-$MOSQUITTO_VERSION.tar.gz" | tar -xz
WORKDIR "mosquitto-$MOSQUITTO_VERSION"
RUN make
RUN make install
RUN ldconfig
WORKDIR /
RUN rm --recursive --force /mosquitto

#RUN apt-get install --yes mosquitto
