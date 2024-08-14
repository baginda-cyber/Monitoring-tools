Monitoring Tools Setup

This repository contains the Docker Compose configuration files for setting up a comprehensive monitoring stack using Prometheus, Grafana, Loki, Promtail, cAdvisor, Node Exporter, and Blackbox Exporter. These tools provide robust metrics collection, visualization, log management, and endpoint probing for monitoring your microservices-based applications in a production environment.

Tools Included
   -  Prometheus: Collects and stores time-series data for metrics from various sources.
   -  Grafana: Visualizes metrics and logs with customizable dashboards and alerts.
   -  Loki: A log aggregation system designed for storing and querying logs efficiently.
   -  Promtail: Collects logs from applications and ships them to Loki.
   -  cAdvisor: Monitors container performance and resource usage.
   -  Node Exporter: Collects hardware and OS metrics from Linux systems.
   -  Blackbox Exporter: Probes endpoints like HTTP, HTTPS, DNS, TCP, and ICMP to monitor their availability and response times.


Setup Instructions to Deploy on server using docker 

1. Clone this repository:
- git clone https://github.com/baginda-cyber/Monitoring-tools.git
- cd Monitoring-tools

2. Configure your environment:

Modify any configuration files if necessary (e.g., prometheus.yml, loki-config.yml, promtail-config.yml) to match your environment.
Ensure that your endpoints and targets are correctly specified in the configuration files.

3. Deploy it!
using command: docker-compose up -d

4. Access the services:

- Grafana: http://localhost:3000
- Prometheus: http://localhost:9090
- Loki: http://localhost:3100
- cAdvisor: http://localhost:8080
- Blackbox Exporter: http://localhost:9115

5. Configuration Details
- Grafana: Configured to connect to Prometheus and Loki as data sources. Dashboards can be created and customized as per the monitoring needs.
- Prometheus: Configured to scrape metrics from Node Exporter, cAdvisor, Blackbox Exporter, and any other services specified in prometheus.yml.
- Loki: Configured to store logs, with Promtail configured as an agent to collect and forward logs.
- cAdvisor: Provides container-level metrics such as CPU, memory, and disk usage.
- Node Exporter: Exposes system-level metrics for Prometheus to scrape.
- Blackbox Exporter: Used to monitor the availability and performance of endpoints.


--------------------------KUBERNETES---------------------------

Setup Instructions to Deploy on server using Kubernetes

This repository contains the Kubernetes manifest files for setting up a comprehensive monitoring stack using Prometheus, Grafana, Loki, Promtail, cAdvisor, Node Exporter, and Blackbox Exporter. These tools provide robust metrics collection, visualization, log management, and endpoint probing for monitoring your microservices-based applications in a production environment.


Tools Included
- Prometheus: Collects and stores time-series data for metrics from various sources.
- Grafana: Visualizes metrics and logs with customizable dashboards and alerts.
- Loki: A log aggregation system designed for storing and querying logs efficiently.
- Promtail: Collects logs from applications and ships them to Loki.
- cAdvisor: Monitors container performance and resource usage.
- Node Exporter: Collects hardware and OS metrics from Linux systems.
- Blackbox Exporter: Probes endpoints like HTTP, HTTPS, DNS, TCP, and ICMP to monitor their availability and response times.


1. git clone https://github.com/baginda-cyber/Monitoring-tools.git
cd Monitoring-tools

2. Apply the Prometheus manifest to your Kubernetes cluster:
- kubectl apply -f kubernetes/prometheus-deployment.yaml

3. Deploying Grafana, Apply the Grafana manifest:
- kubectl apply -f kubernetes/grafana-deployment.yaml :
  Grafana is configured to connect to Prometheus and Loki as data sources. The service is exposed on port 3000.

4. Apply the Loki manifest:
- kubectl apply -f kubernetes/loki-deployment.yaml
  This will set up Loki as a log aggregation service, exposing it on port 3100.

5. Apply the Promtail manifest:
- kubectl apply -f kubernetes/promtail-deployment.yaml

6. Apply the cAdvisor manifest:
- kubectl apply -f kubernetes/cadvisor-deployment.yaml

7. Apply the Node Exporter manifest:
- kubectl apply -f kubernetes/node-exporter-daemonset.yaml

8. Apply the Blackbox Exporter manifest:
- kubectl apply -f kubernetes/blackbox-exporter-deployment.yaml

9. Open the grafana dashboard using your ingress.yaml, because every company had the different config ingrees.




Don't forget to be happy :) 
