# Hamro Tarkari - Kalimati API Performance Testing

Performance testing of the Hamro Tarkari Kalimati API using **Apache JMeter**. This project evaluates API performance under Load and Spike testing scenarios by measuring response time, throughput, latency, error rate, and overall system stability.

---

## Project Overview

**API Tested**

```
GET https://keyvalue.hamrostack.com/kv/get/kalimati_storage::-1
```

This project simulates concurrent users accessing the Kalimati market data endpoint to evaluate:

- Scalability
- Stability
- Throughput
- Response Time
- Error Rate
- Recovery from sudden traffic spikes

---

## Tech Stack

- Apache JMeter 5.6.3
- Ultimate Thread Group Plugin
- HTTP Request Defaults
- Uniform Random Timer
- Aggregate Report
- Summary Report
- View Results Tree

---

## Test Scenario

### Load Test

Gradually increases the number of concurrent users to observe system behavior under normal traffic.

### Spike Test

Introduces sudden increases in traffic to verify API resilience and recovery.

---

## Thread Configuration

| Users | Startup | Hold | Shutdown |
|--------|--------:|-----:|---------:|
| 200 | 10 sec | 20 sec | 20 sec |
| 500 | 10 sec | 200 sec | 10 sec |
| 700 | 20 sec | 160 sec | 10 sec |
| 1500 | 5 sec | 120 sec | 10 sec |

---

# Project Structure

```
Hamro_Tarkari_Performance_Testing/
│
├── API_Kalimati_LoadPerformance.jmx
├── README.md
│
├── reports/
│   ├── dashboard/
│   └── results.jtl
│

```

---

# Prerequisites

- Java 11 or later
- Apache JMeter 5.6.3
- JMeter Plugins Manager
- Ultimate Thread Group Plugin

Verify installation:

```bash
jmeter -v
```

---

# Running the Test (GUI)

Open the test plan:

```bash
jmeter
```

Open:

```
API_Kalimati_LoadPerformance.jmx
```

Click **Start** to execute the test.

---

# Running the Test (CLI)

Execute the test without opening the GUI:

```bash
jmeter -n \
-t API_Kalimati_LoadPerformance.jmx \
-l reports/results.jtl
```

Where:

- `-n` → Non-GUI mode
- `-t` → Test Plan
- `-l` → Result log (.jtl)

---

# Generate HTML Dashboard Report

After execution:

```bash
jmeter -g reports/results.jtl \
-o reports/dashboard
```

Where:

- `-g` → Input JTL file
- `-o` → Output HTML dashboard

---

# Run Test & Generate Report (One Command)

```bash
jmeter -n \
-t API_Kalimati_LoadPerformance.jmx \
-l reports/results.jtl \
-e \
-o reports/dashboard
```

Options:

| Option | Description |
|---------|-------------|
| `-n` | Run without GUI |
| `-t` | Test Plan |
| `-l` | Save Results |
| `-e` | Generate HTML Report |
| `-o` | Report Output Folder |

---

# View the Report

Open:

```
reports/dashboard/index.html
```

in your preferred browser.

---

# Performance Metrics

The following metrics are analyzed:

- Average Response Time
- Minimum Response Time
- Maximum Response Time
- Median
- 90th Percentile
- 95th Percentile
- 99th Percentile
- Throughput
- Requests/Second
- Error Percentage
- Active Threads
- Latency
- Connect Time

---

# Components Used

- Ultimate Thread Group
- HTTP Request Defaults
- HTTP Header Manager
- Uniform Random Timer
- HTTP Request Sampler
- Aggregate Report
- Summary Report
- View Results Tree

---

# Learning Outcomes

- API Performance Testing
- Load Testing
- Spike Testing
- Thread Scheduling
- JMeter CLI Execution
- HTML Dashboard Generation
- Throughput Analysis
- Response Time Analysis
- SLA Monitoring
- Performance Report Interpretation

---

## Sample Commands

Run test:

```bash
jmeter -n -t API_Kalimati_LoadPerformance.jmx -l reports/results.jtl
```

Generate dashboard:

```bash
jmeter -g reports/results.jtl -o reports/dashboard
```

Run and generate dashboard together:

```bash
jmeter -n -t API_Kalimati_LoadPerformance.jmx -l reports/results.jtl -e -o reports/dashboard
```

Check JMeter version:

```bash
jmeter -v
```

# Author

**Er. Sachee Ghimire**

Associate Software Engineer (QA)



---

