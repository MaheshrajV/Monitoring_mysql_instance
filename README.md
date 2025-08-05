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




📊 Access Grafana
Open your browser and navigate to:
👉 http://localhost:3000

Login:

Username: admin

Password: admin

📌 Notes
Ensure MySQL is running locally before starting the containers.

The Prometheus web UI is available at: http://localhost:9090

MySQL Exporter listens on port: 9104
