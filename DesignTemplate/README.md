### System Scale & Throughput Reference

| Requests per Day | Requests/sec | 2 KB (req+resp) | 4 KB (req+resp) |
| :--- | :--- | :--- | :--- |
| **100K**  | 1 | 2.31 KB/s | 4.63 KB/s |
| **1M** | 10 | 23.15 KB/s | 46.30 KB/s |
| **10M** | 100 | 231.48 KB/s | 462.96 KB/s |
| **100M** | 1K | 2.26 MB/s | 4.52 MB/s |
| **1B** | 10K | 22.61 MB/s | 45.23 MB/s |
| **10B** | 100K | |  |
| **100B** | 1M  | |  |

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
