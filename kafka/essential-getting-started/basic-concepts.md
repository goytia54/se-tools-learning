# Basic Concepets

## Kafka Messages
* Event
* Unit of data (row, record, map, blob)
* Treats all as byte array
  * Structure is implemented by the pub/sub
  * size limit exits in kafka (default is 1 mb)

### Message Content
* Key 
  * Not unique
  * used for partitioning
* Value
  * content of the message
  * user defined
* Timestamp
  * Automaticallly timestamped

## Topics
* Hold and manage messages ( file with papers where messages are paper)
* Queue for similar messages
  * Sale transactions, audit logs, video files
* Multiple topics per kafka instance
* Multiple partitions per topic

## Kafka Brokers
* A running instance of kafka
* Receives messages and stores
* Subscription mgmt (heart beat of consumers)
* Topics, partitions and logs mgmt
* Clustering capabilities
* Replication

## Kafka Logs
* Physical files for storing data
* Managed by Kafka brokers
* Multipole files (by broker/topic/partition
* Rolling files (once filled rolled to another file)
  * Only kept for 7 days, can be configurable
* Physical state managment (server.properties)

## Producers
* Client that produces data to Kafka
* Use a kafka client library
* Multplie concurrent producers per topic
* Message key identification
* Message serialization to bytes
* Sync/Async Options

## Consumers
* Consume messages from kakfa
* Consume anytime (streaming or batching)
* Client libraries by programming language
* Multiple concurrent consumer per topic
* workload scaling with consumer groups
* Deserialize bytes to data structures

## Zookeeper (Not needed as much any more)
* Instance could use zookeeper
* Central, realtime information store for kafka
* Broker management
  * broker registry
  * active controller
  * broker failure management
* Topic management 
  * Topic registry
  * Partiion leader management
