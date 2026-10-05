\# Node Exporter



Prometheus Node Exporter exposes Linux system and hardware metrics for monitoring.



\## Configuration



\- Service: `node\_exporter`

\- Service User: `node\_exporter`

\- Port: `9100`

\- Executable: `/usr/local/bin/node\_exporter`

\- Configuration: Default

\- Restart Policy: `always`



\## Metrics



Node Exporter provides system-level metrics including:



\- CPU utilization

\- Memory usage

\- Disk usage

\- Filesystem metrics

\- Network statistics

\- System load

\- Node availability



\## Monitoring Architecture



Node Exporter runs on the monitored EC2 instances.



Frontend EC2 → Node Exporter :9100  

Backend EC2 → Node Exporter :9100  

Observability EC2 → Node Exporter :9100



Prometheus discovers and scrapes these endpoints.



\## Prometheus Integration



Prometheus uses AWS EC2 service discovery to dynamically discover Frontend and Backend instances using their EC2 `Name` tags.

