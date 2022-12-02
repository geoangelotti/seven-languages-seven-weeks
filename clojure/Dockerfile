FROM alpine

RUN apk update && apk add leiningen

WORKDIR /root/app
COPY . .

CMD [ "lein", "repl" ]