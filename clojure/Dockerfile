FROM alpine

RUN apk update && apk add leiningen

WORKDIR /clojure
COPY . .

CMD [ "lein", "repl" ]