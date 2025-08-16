# Monitoring Project (Prometheus + Grafana)

## 📌 Overview
This project sets up a monitoring stack using **Prometheus** and **Grafana** with Docker Compose.  
It collects metrics from different targets (such as Node Exporter, applications, and Prometheus itself) and visualizes them in Grafana dashboards.  

## 📂 Project Structure
devops-intern-project/
│── ansible/
│   ├── inventory.ini          # Ansible inventory file (servers info)
│   ├── setup-webserver.yml    # Playbook for Apache + Node Exporter
│   └── roles/                 # (Optional) future Ansible roles
│
│── monitoring/
│   ├── prometheus.yml         # Prometheus configuration
│   ├── docker-compose.yml     # Prometheus + Grafana docker-compose setup
│   └── dashboards/            # Custom Grafana dashboards JSON
│
│── docs/
│   ├── README.md              # Project explanation
│   └── architecture.png       # Architecture diagram
│
│── .gitignore
│── LICENSE
│── README.md      

## 🚀 How to Run
1. Start the stack:
   ```bash
   docker-compose up -d

