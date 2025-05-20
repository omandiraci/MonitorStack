# Monitoring Stack

A Docker Compose based monitoring solution with the following components:

## Components

- **Prometheus**: Metrics collection and alerting
- **Grafana**: Visualization and dashboards
- **cAdvisor**: Container monitoring
- **Node Exporter**: System metrics exporter

## Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/omandiraci/MonitorStack.git
   ```
2. Start the stack:
   ```bash
   docker-compose up -d
   ```
3. Access the services:
   - Prometheus: http://localhost:9090
   - Grafana: http://localhost:3000 (admin/admin)
   - cAdvisor: http://localhost:8080

## Documentation

For detailed configuration and usage instructions, see the [guide.md](guide.md) file.

## License

MIT
