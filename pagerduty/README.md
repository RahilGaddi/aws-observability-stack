\# PagerDuty Integration



PagerDuty is used for incident notification and escalation in the observability workflow.



\## Alert Flow



Prometheus → Alertmanager → PagerDuty → Incident Notification



\## Integration



Alertmanager sends configured alerts to PagerDuty using a PagerDuty Events API routing key.



The routing key is treated as a secret and is \*\*not stored in this repository\*\*.



Configure it securely at deployment/runtime using:



`PAGERDUTY\_ROUTING\_KEY`



\## Alert Severity



\- Critical alerts are routed to PagerDuty.

\- Alert grouping is based on alert name and instance.

\- Alerts are grouped after a short waiting period to reduce notification noise.

\- Repeated alerts are re-notified at configured intervals.



\## Alerts



The observability stack includes alerts for:



\- Instance availability

\- High CPU utilization

\- High disk usage

\- Unauthorized HTTP requests

