# 📊 MySQL Monitoring Stack

This project sets up a monitoring stack for a **local MySQL server** using:

- **MySQL Exporter** (Container)
- **Prometheus** (Container)
- **Grafana** (Container)

---

## 📦 Components

| Service         | Runs On      | Description                          |
|-----------------|--------------|--------------------------------------|
| MySQL           | Host machine | Local database to monitor            |
| MySQL Exporter  | Docker       | Exposes MySQL metrics to Prometheus |
| Prometheus      | Docker       | Scrapes and stores metrics          |
| Grafana         | Docker       | Visualizes the metrics              |

---

## 📁 Directory Structure

monitoring/
├── .my.cnf # MySQL credentials for exporter
├── prometheus.yml # Prometheus scrape config
├── prometheus-mysql.yml # Docker Compose file
└── grafana/
└── datasource.yml # Grafana provisioning



---

## ✅ Prerequisites

- Docker & Docker Compose installed
- MySQL running on **host machine** at port `3306`
- `.my.cnf` file in the root directory with the following content:

```ini
[client]
user=root
password=your_mysql_password
host=host.docker.internal
port=3306


```
##🚀 Running the Stack

Step 3: Start the Monitoring Stack
docker compose up -d

Check containers:
docker ps
Prometheus → http://localhost:9090

Grafana → http://localhost:3000

Default Grafana login: admin / admin

📊 Step 4: Grafana Setup
Go to Settings > Data Sources

Add a new Prometheus data source:
URL: http://prometheus:9090

Import a MySQL dashboard:
Go to Dashboard > Import
Use Dashboard ID: 7362 or search for MySQL Overview

🧪 Test Metrics
Check mysqld_exporter metrics via:
curl http://localhost:9104/metrics
You should see metrics like mysql_global_status_threads_connected, etc.

🧹 To Stop Everything
docker compose down

 Access Grafana
Open your browser and navigate to:
👉 http://localhost:3000

Login:
Username: admin
Password: admin

📌 Notes
Ensure MySQL is running locally before starting the containers.

The Prometheus web UI is available at: http://localhost:9090

MySQL Exporter listens on port: 9104
