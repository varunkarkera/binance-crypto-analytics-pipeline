# Binance Crypto Analytics Pipeline

## 1. Goal

The goal is to build an ETL pipeline for ingesting crypto market, order, account, and risk data and making it available for analytics.

The design focuses on high-volume event ingestion, reliable processing, historical analysis, and near real-time dashboards.

## 2. Data Sources

The simplified pipeline considers:

- Market and trade events
- Order events
- Account activity
- Fees and commissions
- Risk and liquidation events

Data can arrive through REST APIs, WebSockets, or internal event producers.

## 3. Architecture

```text
Binance Data Sources
        |
        v
 REST / WebSocket
        |
        v
     Kafka
        |
        +---------> S3 Raw Data
        |
        v
   Spark + Airflow
        |
        v
    ClickHouse
        |
        v
 Grafana / SQL / BI
