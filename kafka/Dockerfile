FROM golang:1.10
RUN git clone https://github.com/DataDog/kafka-kit.git src/github.com/DataDog/kafka-kit
RUN go get github.com/jamiealquiza/envy
RUN go get github.com/samuel/go-zookeeper/zk
RUN env GOOS=linux GOARCH=amd64 go install github.com/DataDog/kafka-kit/cmd/topicmappr


FROM solsson/kafka:1.1
# FROM confluent/cp-kafka:2.0
RUN apt-get update && apt-get install -y wget --no-install-recommends; \
    rm -rf /var/lib/apt/lists/*; \
    rm -rf /var/log/dpkg.log /var/log/alternatives.log /var/log/apt
COPY --from=0 /go/bin/topicmappr bin/topicmappr
RUN chmod +x bin/topicmappr
