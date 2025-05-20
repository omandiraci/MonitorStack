# Monitoring Stack

This repository contains a Docker Compose configuration for a monitoring stack with the following components:

## Components

1. **Prometheus**
   - Monitoring and alerting toolkit
   - Port: 9090
   - Configuration file: `prometheus_config/prometheus.yml`

2. **Grafana**
   - Visualization and dashboard platform
   - Port: 3000
   - Default credentials: admin/admin

3. **cAdvisor**
   - Container monitoring tool
   - Port: 8080
   - Monitors Docker containers

4. **Node Exporter**
   - Hardware and OS metrics exporter
   - Port: 9100
   - Collects system metrics

## Getting Started

1. Clone this repository
2. Run the stack:
   ```bash
   docker-compose up -d
   ```
3. Access the services:
   - Prometheus: http://localhost:9090
   - Grafana: http://localhost:3000
   - cAdvisor: http://localhost:8080
   - Node Exporter: http://localhost:9100

## Configuration

To configure Prometheus, edit the `prometheus_config/prometheus.yml` file.

## License

MIT
