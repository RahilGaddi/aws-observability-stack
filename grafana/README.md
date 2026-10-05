\# Grafana



Grafana is used to visualize infrastructure and application metrics collected by Prometheus.



\## Configuration



\- Service: `grafana-server`

\- Service User: `grafana`

\- Port: `3000`

\- Executable: `/usr/share/grafana/bin/grafana server`

\- Data Source: Prometheus

\- Prometheus Endpoint: `http://localhost:9090`



\## Observability



Grafana dashboards are used to monitor:



\- CPU utilization

\- Memory utilization

\- Disk usage

\- Node Exporter metrics

\- Frontend instances

\- Backend instances

\- Prometheus health



\## Access



For a private EC2 monitoring server, Grafana can be accessed through AWS Systems Manager port forwarding rather than exposing port `3000` publicly.

