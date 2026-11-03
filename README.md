# Kafka Topic Setup Exercise

This project sets up a minimal Kafka cluster with ZooKeeper and creates the required topics for the pharmacy domain.

## Requirements

- Docker Engine
- Docker Compose

## Start the infrastructure

```bash
docker compose up -d
```

## Create topics

```bash
bash scripts/create-topics.sh
```

## Topics created

- `medicine-stock-events` — 3 partitions, replication factor 1
- `medicine-price-updates` — 1 partition, replication factor 1
- `pharmacy-notifications` — 2 partitions, replication factor 1

## Check from the CLI

```bash
docker exec kafka /opt/bitnami/kafka/bin/kafka-topics.sh --bootstrap-server localhost:9092 --list
docker exec kafka /opt/bitnami/kafka/bin/kafka-topics.sh --bootstrap-server localhost:9092 --describe --topic medicine-stock-events
```

## Stop the stack

```bash
docker compose down -v
```
