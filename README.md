# real_time_data_ingestion_pipeline

### README for CDC Using Kafka and MySQL (Focusing on Transactions Data)

---

## Overview

This project showcases **Change Data Capture (CDC)** for streaming transaction data from a MySQL database to Kafka in real time. By leveraging **Debezium**, any changes made to the `transactions` table are captured and sent to Kafka topics for further processing.

---

## Transactions Data

The **`transactions`** table is the focal point of this project and includes the following fields:

- **`id`**: A unique identifier for each transaction.  
- **`name`**: A label or description of the transaction.  
- **`amount`**: The monetary value involved in the transaction.  
- **`timestamp`**: The date and time when the transaction occurred.

Example use cases include tracking real-time transaction flows, fraud detection, or analyzing financial trends.

---

## Key Features

- **Real-Time Data Capture**: Tracks `INSERT`, `UPDATE`, and `DELETE` operations on the transactions table.  
- **Event Streaming**: Streams captured changes to Kafka topics, enabling event-driven architectures.  
- **Data Replication**: Maintains consistency between the MySQL database and downstream systems.

---

## Steps to Extract Transactions Data Using CDC

### 1. **Prepare MySQL for Change Data Capture**

- Enable MySQL’s binlog functionality, which is required for CDC.
- Configure binlog to use row-level logging for capturing detailed data changes.
- Ensure a user with the necessary permissions is available to access the MySQL binlog.

---

### 2. **Set Up Kafka Connect**

- Install and configure Kafka Connect in distributed mode to enable data streaming.
- Verify that Kafka Connect is operational and accessible.

---

### 3. **Configure the Debezium Connector**

- Deploy the MySQL connector via Kafka Connect, specifying the necessary database and table configurations.
- Define which database and table (e.g., `transactions`) should be monitored for changes.

---

### 4. **Stream Data to Kafka Topics**

- Once the connector is running, any changes to the `transactions` table will be automatically published to Kafka topics.
- These topics contain the captured data, including the state of rows before and after changes, and metadata about the operation performed.

---

### 5. **Monitor the Kafka Stream**

- Consume and validate the streamed data using a Kafka consumer tool or a compatible system.
- Ensure that all `INSERT`, `UPDATE`, and `DELETE` operations are accurately captured and streamed.

---

### 6. **Export Data to a File**

- Use a Kafka sink connector or a custom consumer application to persist streamed data into a file format (e.g., CSV or JSON).
- Ensure that the exported file reflects all changes in the `transactions` table for further processing or archival.

---

## Use Cases

- **Real-Time Analytics**: Monitor financial transactions as they occur for actionable insights.  
- **Fraud Detection**: Analyze transaction patterns for potential fraud in real time.  
- **Data Warehousing**: Replicate transaction data into a warehouse for batch analysis and reporting.  

---

## Best Practices

- Always test CDC in a development environment before deploying to production.  
- Monitor connector performance and Kafka topic offsets regularly to ensure reliable data capture.  
- Secure sensitive data using encryption and access control measures.  

---

## Next Steps

- Set up a data pipeline to transform and load streamed data into a reporting or analytics platform.  
- Expand CDC to additional tables or databases as needed.  
- Implement alerting mechanisms for anomalies in transaction patterns.  

---

## References

- Consult the official Debezium and Kafka documentation for advanced configurations and troubleshooting.  
- Explore MySQL’s replication and binlog settings for optimizing CDC performance.  
