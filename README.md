![](https://rawgit.com/appu3239/java-kafka/master/spring-kafka-demo/src/main/resources/readme_img.png)
# Knowledge
## Kafka™
"Kafka is used for building real-time data pipelines and streaming apps. It is horizontally scalable, fault-tolerant, wicked fast, and runs in production in thousands of companies"

## Breakdown
- Horizontally scalable - Provide means for high availability of application without causing any downtime.
- Fault Tolerant - Property of an application in which the service continue to work even if there are any faults within the application.
- Wicked fast - duh :fire:

As a streaming platform, it lets you `publish` and `subscribe` to streams of data which is very similar to messaging queue like JMS (Java message service). Kafka can store streams of data for a time period in a fault tolerant way.

Kafka is a good fit for the below use cases
 1. messaging
 2. Website activity tracking
 3. Time Series application events
 4. Application metrics
 5. Log aggregation
 6. Stream Processing*

*Stream processing is supported as of 0.10 vesion of Kafka*

### Guarantees:

- Messages sent by a producer to a particular topic partition will be appended in the order they are sent. That is, if a record M1 is sent by the same producer as a record M2, and M1 is sent first, then M1 will have a lower offset than M2 and appear earlier in the log.
- A consumer instance sees records in the order they are stored in the log.
- For a topic with replication factor N, we will tolerate up to N-1 server failures without losing any records committed to the log.

# Goal
Write a java client for kafka to explore kafka's `producer`, `consumer`, `streams` and `connect` APIs.

- Create a message in json and publish them using kafka producer
- Consume this message from a topic and write it to a failures
- Consume this message from topic and transform and write it to a file using stream api
- Try using connect api if necessary

## Setup
- Download kafka binary: https://www.apache.org/dyn/closer.cgi?path=/kafka/0.10.1.1/kafka_2.10-0.10.1.1.tgz

- Start Zookeeper
```bash
bin/zookeeper-server-start.sh config/zookeeper.properties
```
- Start Kafka broker
```bash
bin/zookeeper-server-start.sh config/server.properties
```
## See also
- Publish and subscribe pattern - https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
