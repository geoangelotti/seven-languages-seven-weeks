FROM ubuntu:latest

RUN apt-get update && \
	DEBIAN_FRONTEND=noninteractive \
	apt install -y tzdata && \
	apt-get install -y \
	build-essential \
	git \
	cmake


WORKDIR /src
RUN git clone --recursive https://github.com/IoLanguage/io.git

WORKDIR /src/io
RUN mkdir build 
WORKDIR /src/io/build
RUN cmake ..
RUN make
RUN make install

WORKDIR /root/app
COPY . .

ENTRYPOINT [ "bash" ]
