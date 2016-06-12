FROM debian

RUN apt-get update
RUN apt-get install --yes build-essential \
	libssl-dev \
	libc-ares-dev \
	uuid-dev \
	curl

ENV MOSQUITTO_VERSION 1.4.9
RUN mkdir /mosquitto && \
	cd /mosquitto && \
	curl "http://mosquitto.org/files/source/mosquitto-$MOSQUITTO_VERSION.tar.gz" | tar -xz

RUN cd "/mosquitto/mosquitto-$MOSQUITTO_VERSION" && \
	make && \
	make install && \
	ldconfig && \
	cd / && \
	rm --recursive --force /mosquitto

#RUN apt-get install --yes mosquitto
