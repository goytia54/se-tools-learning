# CLI

## `/opt/bitnami/kafka`
* `config` contains configuration, restarting container with override these
* `logs` log files generated by kafka
* `bin` shell scripts for management

## Creating topics
```
./kafka-topics.sh --bootstrap-server localhost:9092 --create --topic kafka.learning.tweets --partitions 1
```

## Exploring topics 
```
./kafka-topics.sh --bootstrap-server localhost:9092 --list
```

```
./kafka-topics.sh --bootstrap-server localhost:9092 --describe
```

## Topic Managments
* Can modify and delete topics
* Can use the zookeepr client to explore the brokers

## Sending data to a topic
You can use a tool like jq to send json to a topic

* `jq -rc . sampledata.json | kafka-console-producer --broker-list localhost:9092 --topic  stream-test-topic`
  * `-r` raw output
  * `-c` concise
