# Real-Time Financial Data Pipeline  

## Description  
This project implements a real-time data pipeline to capture, process, and analyze financial transaction data. By leveraging MySQL, Kafka, and Debezium, it streams database changes into Kafka topics and processes them for storage or analytics.  


## Features  
- **Change Data Capture (CDC)**: Captures real-time `INSERT`, `UPDATE`, and `DELETE` events.  
- **Kafka Streaming**: Streams high-volume data for distributed processing.  
- **Data Export**: Saves processed data to files or databases for reporting.  


## Workflow  
1. **Data Source**: MySQL `transactions` table containing `id`, `name`, `amount`, and `timestamp`.  
2. **CDC Integration**: Debezium reads MySQL binlogs and streams changes to Kafka.  
3. **Processing**: Kafka consumers process data and export it for further use.  


## Setup Steps  
1. **MySQL Configuration**: Enable binlogs and setup Debezium for CDC.  
2. **Kafka Environment**: Configure Kafka brokers, Zookeeper, and Kafka Connect.  
3. **Deploy Debezium Connector**: Monitor MySQL changes and publish to Kafka topics.  
4. **Consumer Setup**: Process Kafka messages and store/export data.  

## Future Enhancements  
- Integration with a data warehouse for advanced reporting.  
- Visualization dashboards for real-time insights.  
- Support for additional financial datasets.  
