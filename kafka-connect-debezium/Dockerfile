FROM confluentinc/cp-kafka-connect:5.0.0

ENV DEBEZIUM_VERSION=0.8.1.Final \
    MAVEN_REPO_CORE="https://repo1.maven.org/maven2" \
    MAVEN_REPO_INCUBATOR="https://repo1.maven.org/maven2" \
    CONNECTOR=mysql \
    KAFKA_CONNECT_PLUGINS_DIR=/usr/share/java

RUN curl -fSL -o /tmp/plugin.tar.gz \
  $MAVEN_REPO_CORE/io/debezium/debezium-connector-$CONNECTOR/$DEBEZIUM_VERSION/debezium-connector-$CONNECTOR-$DEBEZIUM_VERSION-plugin.tar.gz &&\
  tar -xzf /tmp/plugin.tar.gz -C $KAFKA_CONNECT_PLUGINS_DIR &&\
  rm -f /tmp/plugin.tar.gz
