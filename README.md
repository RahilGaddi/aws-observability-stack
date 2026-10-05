\# AWS Observability Stack



A hands-on AWS observability and monitoring implementation using Prometheus, Grafana, Alertmanager, Node Exporter, and PagerDuty.



The stack monitors AWS EC2-based application infrastructure, collects system metrics, visualizes them through Grafana, evaluates alert rules with Prometheus, and routes critical incidents through Alertmanager to PagerDuty.



\---



\## Architecture



```text

&#x20;                   AWS Cloud

&#x20;                      |

&#x20;       +--------------+--------------+

&#x20;       |                             |

&#x20;  Frontend EC2                   Backend EC2

&#x20;  Nginx + App                    Node.js + PM2

&#x20;       |                             |

&#x20;Node Exporter :9100             Node Exporter :9100

&#x20;       |                             |

&#x20;       +--------------+--------------+

&#x20;                      |

&#x20;                      v

&#x20;             Observability EC2

&#x20;                      |

&#x20;             +--------+--------+

&#x20;             |                 |

&#x20;       Prometheus :9090   Node Exporter :9100

&#x20;             |

&#x20;       +-----+------+

&#x20;       |            |

&#x20;       v            v

&#x20;    Grafana     Alertmanager

&#x20;     :3000          :9093

&#x20;                      |

&#x20;                      v

&#x20;                  PagerDuty

&#x20;                      |

&#x20;                      v

&#x20;            Incident Notification

