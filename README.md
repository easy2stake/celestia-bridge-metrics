# celestia-bridge-metrics

## Overview
`celestia-bridge-metrics` is a Prometheus exporter designed for simplicity and ease of use, catering specifically to Celestia bridge instances.

**Full monitoring stack here:** [https://github.com/P-OPSTeam/celestia-tools/tree/main/grafana](https://github.com/P-OPSTeam/celestia-tools/tree/main/grafana)
## Configuration
The exporter is pre-configured to transmit telemetry data to the Celestia server. Refer to the configuration in `conf/otel-collector-config.yaml`:

```yaml
exporters:
  otlphttp:
    endpoint: https://otel.celestia.observer
```

## Usage
To enable metrics collection, initialize your Celestia bridge with the following parameters:
```sh
--metrics --metrics.tls=false --metrics.endpoint=127.0.0.1:4318
```
Start the service with the command:
```sh
docker-compose up -d
```
### Access metrics at the following endpoints:
- **Exporter metrics**: Accessible at http://127.0.0.1:8888/metrics
- **Bridge metrics**: Accessible at http://127.0.0.1:8889/metrics

### Security Warning
:warning: **Exposure Risk**: If your machine is exposed to the internet (has a public IP), the Docker network will expose your metrics ports to the internet. If you're unsure about securing your setup, please seek guidance through the appropriate channels.


## Contact
For support issues and feature requests, please use the GitHub issue tracker.
