# Python

### Cài đặt thư viện
```
pip install kafka-python
```
### Producer
```
from kafka import KafkaProducer
import time

producer = KafkaProducer(bootstrap_servers='localhost:9092')

producer.send(message)

producer.flush()
```
### Consumer
```
from kafka import KafkaConsumer

consumer = KafkaConsumer(topic, bootstrap_servers='localhost:9092')

for message in consumer:
    print(message)
```

# Spring Boot
### Thư viện
```
<dependency>
  <groupId>org.springframework.kafka</groupId>
  <artifactId>spring-kafka</artifactId>
</dependency>
```
### Cấu hình application.properties
```
spring.kafka.bootstrap-servers=localhost:9092
```
### Producer
```
kafkaTemplate.send(topic, message);
```
### Consumer
```
@KafkaListener(topics = topic)
public void listen(String message) {
    System.out.println(message);
}
```
