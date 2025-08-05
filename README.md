****************************************************************************************MySQL Monitoring Stack*****************************************************************************************


mysql(local host) 
mysql exporter(on container) 
prometheus(on container) 
grafana(on container)

📁 Directory Structure

monitoring
├── .my.cnf
├── prometheus.yml
├── prometheus-mysql.yml
└── grafana/
    └── datasource.yml

✅ Final Steps
✅ Start Docker containers:
cd ~/Desktop/monitoring/
docker compose -f prometheus-mysql.yml up -d


✅ Open Grafana:
http://localhost:3000
