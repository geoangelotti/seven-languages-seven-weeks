FROM ubuntu
RUN apt-get update && apt-get install build-essential software-properties-common -y && apt-add-repository -y ppa:rael-gc/rvm && apt-get update && apt-get install rvm -y
RUN /usr/share/rvm/bin/rvm install 1.8
ENV PATH "$PATH:/usr/share/rvm/rubies/ruby-1.8.7-p374/bin"

WORKDIR /root/app
COPY . .

CMD ["irb"]
