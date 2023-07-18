FROM ubuntu:latest

RUN apt-get update && \
	DEBIAN_FRONTEND=noninteractive \
	apt-get install -y gcc \
	git \
	make

WORKDIR /src
RUN git clone https://github.com/didoudiaz/gprolog.git

WORKDIR /src/gprolog/src
RUN ./configure
RUN make

WORKDIR /prolog
COPY . .

ENTRYPOINT [ "bash" ]
