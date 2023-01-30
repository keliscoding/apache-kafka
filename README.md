# Apache Kafka

## Instalando o Kafka localmente
After downloading apache kafka tgz, navigate to its dir and type:
```
./bin/windows/zookeeper-server-start.bat ./config/zookeeper.properties
```
after, insert the following command to start kafka server:
```
./bin/windows/kafka-server-start.bat ./config/server.properties
```

Kafka's default port is **9092**.


## Topics
### Create topics
```
 .\bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic <nome>
```

Segundo o próprio kafka, não é pra misturar _ com . na hora de nomear os tópicos.  
> WARNING: Due to limitations in metric names, topics with a period ('.') or underscore ('_') could collide. To avoid issues it is best to use either, but not both.

### List Topics:
```
.\bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092

```

## Producers

### Create a producer
```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic <topic-name>
```

## Consumers

### Create a consumer

```
 .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic <topi-name> --from-beginning
```

you must add a param indicating where the consumer must begin to consume your messages, in this case, ```--from-beginning```