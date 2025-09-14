## Apache Kafka Setup on AWS EC2
description: One-shot guide to install and run Apache Kafka on AWS EC2 instance.

## Install Java
    commands:
      - sudo yum install java-1.8.0-openjdk -y
      - java -version

## Download & Extract Kafka
    commands:
      - wget https://downloads.apache.org/kafka/3.3.1/kafka_2.12-3.3.1.tgz
      - tar -xvf kafka_2.12-3.3.1.tgz
      - cd kafka_2.12-3.3.1

## Start ZooKeeper
    commands:
      - bin/zookeeper-server-start.sh config/zookeeper.properties

## Start Kafka Broker
    notes: Edit server.properties → advertised.listeners=PLAINTEXT://<EC2-Public-IP>:9092
    commands:
      - export KAFKA_HEAP_OPTS="-Xmx256M -Xms128M"
      - sudo nano config/server.properties
      - bin/kafka-server-start.sh config/server.properties

## Create Topic
    commands:
      - bin/kafka-topics.sh --create --topic demo_topic --bootstrap-server <EC2-Public-IP>:9092 --replication-factor 1 --partitions 1

## Start Producer
    commands:
      - bin/kafka-console-producer.sh --topic demo_topic --bootstrap-server <EC2-Public-IP>:9092

##Start Consumer
    commands:
      - bin/kafka-console-consumer.sh --topic demo_topic --bootstrap-server <EC2-Public-IP>:9092 --from-beginning

result: |
  Producer sends messages → Consumer receives them in real-time.
  Kafka cluster runs on AWS EC2 with ZooKeeper + Broker.

## TECH USED 
  - Apache Kafka
  - AWS EC2
  - ZooKeeper
  - Java (OpenJDK)

## Note
   - Download AWS and test wit --version in AWS CLI before topic creation
   - Producer, Consumer , AWS should have different sessions in Powershell.
   -  Stop/Terminate Instances after sucessfully finished.

