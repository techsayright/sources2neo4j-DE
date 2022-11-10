FROM confluentinc/cp-kafka-connect-base

RUN confluent-hub install --no-prompt debezium/debezium-connector-postgresql:latest \
    && confluent-hub install --no-prompt debezium/debezium-connector-mysql:latest \
    && confluent-hub install --no-prompt debezium/debezium-connector-mongodb:latest\
    && confluent-hub install --no-prompt neo4j/kafka-connect-neo4j:5.0.0

ADD connectors /etc/kafka-connect/connectors

WORKDIR /etc/kafka-connect/connectors

CMD ["./register_connectors.sh"]