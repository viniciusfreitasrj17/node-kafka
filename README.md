# Basic Command to uise Kafka

## Run

```sh
docker-compose up
```

## Create Topic

```sh
docker exec -it node-kafka_kafka_1 ./opt/bitnami/kafka/bin/kafka-topics.sh --create --bootstrap-server 0.0.0.0:9092 --replication-factor 1 --partitions 1 --topic TOPIC_NAME
```

## List Topics

```sh
docker exec -it node-kafka_kafka_1 ./opt/bitnami/kafka/bin/kafka-topics.sh --list --bootstrap-server 0.0.0.0:9092
```

## Producer in Topic

```sh
docker exec -it node-kafka_kafka_1 ./opt/bitnami/kafka/bin/kafka-console-producer.sh --bootstrap-server 0.0.0.0:9092 --topic TEST_TOPIC
```

## Consumer in Topic

```sh
docker exec -it node-kafka_kafka_1 ./opt/bitnami/kafka/bin/kafka-console-consumer.sh --bootstrap-server 0.0.0.0:9092 --topic TEST_TOPIC
docker exec -it node-kafka_kafka_1 ./opt/bitnami/kafka/bin/kafka-console-consumer.sh --bootstrap-server 0.0.0.0:9092 --topic TEST_TOPIC --from-beginning
```
