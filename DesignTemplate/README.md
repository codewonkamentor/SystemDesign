## Calculation
### System Scale & Throughput Reference

| Requests per Day | Requests/sec        | 2 KB (req+resp) | 4 KB (req+resp) |
|------------------|--------------------|------------------|------------------|
| 100K (10^5)      | 1.16 (≈10^0)       | 2.31 KB/s        | 4.63 KB/s        |
| 1M (10^6)        | 11.57 (≈10^1)      | 23.15 KB/s       | 46.30 KB/s       |
| 10M (10^7)       | 115.74 (≈10^2)     | 231.48 KB/s      | 462.96 KB/s      |
| 100M (10^8)      | 1.16K (≈10^3)      | 2.31 MB/s        | 4.63 MB/s        |
| 1B (10^9)        | 11.57K (≈10^4)     | 23.15 MB/s       | 46.30 MB/s       |
| 10B (10^10)      | 115.74K (≈10^5)    | 231.48 MB/s      | 462.96 MB/s      |
| 100B (10^11)     | 1.16M (≈10^6)      | 2.31 GB/s        | 4.63 GB/s        |


**Unit Conversion:** `1 character = 1 byte = 8 bits`

### Data Size Conversion Table

| Input Size | In Bytes | Best Unit | Converted Value |
| :--- | :--- | :--- | :--- |
| **1K Bytes** | $10^3$ B | KB | 1 KB |
| **10K Bytes** | $10^4$ B | KB | 10 KB |
| **100K Bytes** | $10^5$ B | KB | 100 KB |
| **1M Bytes** | $10^6$ B | MB | 1 MB |
| **10M Bytes** | $10^7$ B | MB | 10 MB |
| **100M Bytes** | $10^8$ B | MB | 100 MB |
| **1B Bytes** | $10^9$ B | GB | 1 GB |

---

### Capacity Planning Formulas

* **Peak Traffic Estimation:** Use a **2x multiplier** for headroom.
* **Avg Payload Size:** Typical values: `2KB` / `4KB` / `1KB`.
* **Total System Bandwidth:** $\text{RequestsPerSec} \times \text{Avg Payload size}$


## BackendDatabase Selection

### Timeseries use case choose Timeseries database
Example use cases: Cloudwatch monitoring, Ad click aggregator
1. Influx DB: General Purpose Analytics and IoT.
1. Prothemus: Cloud-Native Monitoring
1. ElasticSearch: Log-based time-series data and trace analytics
   
### High-volume text, partial matches, or "fuzzy" search
Example use cases: Google Search for web pages for search query, Tweet search in twitter.
1. ElasticSearch

### High-volume write system
Example use cases: Chat system like Whatsapp, Facebook
1. Cassanda 
1. Dyanmodb
1. Google Bigtable

### Geospatial data
1. Redis with H3 index
2. Redis with GeoHash
3. REdis with S3 index
1. Google S2 Based Databases: Google Bigtable / HBase, Google Spanner,
2. H3 Based Databases: ClickHouse, Elasticsearch / OpenSearch

### Strong consistent with ACID props
Example use case: Payment system. Relational databases are used
1. PostgreSQL
1. MySQL
1. Oracle
1. CockroachDB

## Common Design Pattenr

### Last mile async fan out delivery 
1. Redis PubSub
1. Redis Stream
1. Aache Kafka

### Streaming
Use case: real-time counters, gaming leaderboards, or high-frequency trading.
1. Redis
1. Aerospike
1. Apache Kafka

## Data storage layer Optimization 
### Compression for chat/post data
1. Binary Serialization,
1. Dictionary Compression,
1. Domain-Specific Encoding
