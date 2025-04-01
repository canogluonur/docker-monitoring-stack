# docker Monitoring Stack

A simple, containerized monitoring solution with Prometheus, Alertmanager, Grafana, and Node Exporter.

## Requirements

- Docker and Docker Compose
- 1GB RAM and 10GB disk space (minimum)

## Quick Start

1. Clone the repository:
```bash
git clone https://github.com/username/docker-monitoring-stack.git
cd docker-monitoring-stack
```

2. Configure your Slack webhook in `alertmanager.yml`:
```yaml
slack_configs:
  - api_url: 'https://hooks.slack.com/services/YOUR_SLACK_WEBHOOK_URL'
```

3. Start the stack:
```bash
docker-compose up -d
```

4. Access the interfaces:
   - Prometheus: http://localhost:9090
   - Alertmanager: http://localhost:9093
   - Grafana: http://localhost:3000 (admin/admin)

## Features

- Host metrics monitoring (CPU, Memory, Disk, Network)
- Preconfigured alerting rules with Slack notifications
- Grafana dashboard integration


### Recommended Grafana Dashboards

- Node Exporter Full (ID: 1860)
- Node Exporter Quickstart (ID: 11074)

## Troubleshooting

- Check container status: `docker-compose ps -a `
- View logs: `docker logs prometheus`
- Verify targets in Prometheus UI: http://localhost:9090/targets

## Project Structure

```
├── docker-compose.yml        # Container definitions
├── prometheus.yml            # Prometheus configuration
├── node-exporter-alerts.yml  # Alert rules
├── alertmanager.yml          # Alertmanager configuration
└── grafana/                  # Grafana data and config
    └── datasources.yml       # Grafana datasource configuration
```