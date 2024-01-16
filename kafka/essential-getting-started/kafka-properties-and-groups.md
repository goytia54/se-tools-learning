# Kafka Properties and Groups

## Partitions
* Each topic can hav 1-n partitions
* Allow kafka to scale (horizontal)
* Partitions have seperate log files
* Each partition has a leader broker
* Enable consumers to share workloads through consumer groups
* Partitions can be replicated by increasing latency
* Number of partitions can not be changed after

## Publish Messages with keys
properties used to specify the key and value
```
--property "parse.key=true"  --property "key.separator=:" 
```

## Consumer Group
* A group of consumers who share a topic workload 
* Each message only sent to one message in consumer group
* Consumers split workload through partitions
  * No of partitions >= no. of consumers
* Each group only gets the message once

## Consumer Offsets
* Number to track message consumption by consumer and partion
* Broker keeps track of what is sent and acknowledged
* Current offset: last message sent to a given consumer
* Committed offset: last message acknowledged by consumer
* Broker resends uncommitted messages in case of failure/timeout
* Ensures at least one delivery

### Consumer example
* If consumer crashes and not committed, another consumer will receive another message to commit message

### LAG
* Difference between current offset and commited offset
