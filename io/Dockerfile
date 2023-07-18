FROM ubuntu:latest

RUN apt-get update && \
	DEBIAN_FRONTEND=noninteractive \
	apt-get install -y tzdata \
	build-essential \
	git \
	cmake \
	pkg-config \
	libreadline-dev 


WORKDIR /src
RUN git clone --recursive https://github.com/IoLanguage/io.git

WORKDIR /src/io
RUN mkdir build 
WORKDIR /src/io/build
RUN cmake ..
RUN make
RUN make install

WORKDIR /src
RUN git clone https://github.com/IoLanguage/eerie.git

WORKDIR /src/eerie
ENV EERIEDIR=/root/.eerie
RUN ./install_unix.sh
ENV PATH=$PATH:$EERIEDIR/base/bin:$EERIEDIR/activeEnv/bin
RUN eerie install https://github.com/IoLanguage/ReadLine.git

WORKDIR /io
COPY . .

ENTRYPOINT [ "bash" ]
