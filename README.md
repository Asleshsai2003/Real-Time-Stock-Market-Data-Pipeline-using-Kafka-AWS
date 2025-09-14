# ⚡ Real-Time Stock Market Data Pipeline (Kafka + AWS)

This project showcases a **real-time data ingestion pipeline** where stock market data is streamed using **Apache Kafka** and stored in **Amazon S3** for analytics.

---

## 🔧 Tech Stack
- **Python** (kafka-python, boto3)  
- **Apache Kafka** (Producers & Consumers)  
- **AWS EC2** (Kafka deployment)  
- **Amazon S3** (cloud storage)  
- **AWS CLI** (configuration & bucket management)  
- **Jupyter Notebook** (development & testing)  

---

## 🚀 Workflow
1. **Producer** publishes stock market data to a Kafka topic.  
2. **Kafka Broker (EC2)** handles real-time streaming.  
3. **Consumer** pulls messages and pushes them to **Amazon S3**.  
4. Managed and tested with **AWS CLI**.

 
---

## 🎯 Key Highlights
- Built a **real-time streaming pipeline** with **Kafka on AWS**.  
- Automated ingestion into **S3 buckets** using Python & Boto3.  
- Configured and validated services via **AWS CLI**.  
- End-to-end cloud-native deployment highlighting **scalability & fault tolerance**.

## Dataset 
You can use any dataset, we are mainly interested in operation side of Data Engineering (building data pipeline)

Here is the dataset used in the video - https://github.com/darshilparmar/stock-market-kafka-data-engineering-project/blob/main/indexProcessed.csv
 

