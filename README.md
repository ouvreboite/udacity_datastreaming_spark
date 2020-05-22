# udacity_datastreaming_spark
This project is part of Udacity's Datastreaming course. It is a demonstrator for a data pipeline around Kafka and Spark that allows us to analyze a real-world dataset of the SF Crime Rate, extracted from kaggle, to provide statistical analysis using Apache Spark Structured Streaming.

## Prerequisites
* Spark 2.4.3
* Scala 2.11.x
* Java 1.8.x
* Kafka build with Scala 2.11.x
* Python 3.6.x or 3.7.x

## Running and Testing
1.Launch Zookeeper (mandatory for Kafka):

```/usr/bin/zookeeper-server-start config/zookeeper.properties```

2.Launch the Kafka server:

```/usr/bin/kafka-server-start config/server.properties```

2.Feed the Kafka topics

```python kafka_server.py```

Check the topic is correctly fed by using the kafka console consumer

```kafka-console-consumer --topic "sanfrancisco.police.calls" --from-beginning --bootstrap-server localhost:9092```

3.Submit the Spark job:

```spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.4 --master local[*] data_stream.py```
