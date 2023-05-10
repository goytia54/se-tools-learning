# Introduction

## Message Queues
* Sender -> Receiver (exchange data)
  * agree on data contract
* Sender -> 3 Receivers 
* Mulitple Sender and Multiple Receivers
* Publisher and Subscripters subscribe to message queues

### Pub-Sub Advantages
* Decoupling of pub sub (easy changes)
* Scaling (N+1)
* Back pressure handling
* Reliability

## What is Kafka?
* Events/Messages Streming Platform
* Critical piece of big data puzzle
* Producers push messages
* Consumers receive the messages

### Functions
* Collection
* Storage
* Transport
* Distribution

### Benefits of Kafka
- High Throughput
- Low Latency
- Fault Tolerance
- Decoupling
- Back Pressure handling (holding data until it consumes)
- Streaming and batching

### Kafka Use Cases
* Async messaging
* Realtime stream processing (trigger real time actions)
* Logging and Monitoring
* Event Sourcing
* Realtime Analytics
