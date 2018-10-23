# kafka-stream
kafka-stream

https://github.com/simplesteph/kafka-streams-course

# list
kafka-topics.bat --zookeeper localhost:2181 --list

# create
kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic streams-wordcount-output

# producer
kafka-console-producer.bat --broker-list 127.0.0.1:9092 --topic streams-plaintext-input

# consumer
kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic streams-plaintext-input --from-beginning

# consumer serdes
kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic wordcount-output --from-beginning -formatter kafka.tools.DefaultMessageFormatter --property print.key=true --property print.value=true --property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer  --property value.deserializer=org.apache.kafka.common.serialization.LongDeserializer
