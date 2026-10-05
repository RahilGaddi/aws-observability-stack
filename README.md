\# AWS Observability Stack



A hands-on AWS observability and monitoring implementation using Prometheus, Grafana, Alertmanager, Node Exporter, and PagerDuty.



The stack monitors AWS EC2-based application infrastructure, collects system metrics, visualizes them through Grafana, evaluates alert rules with Prometheus, and routes critical incidents through Alertmanager to PagerDuty.



\---



\## Architecture



```text

                        AWS Cloud

                            |

             +--------------+--------------+

             |                             |

         Frontend EC2                   Backend EC2

         Nginx + App                    Node.js + PM2

             |                             |

        Node Exporter :9100             Node Exporter :9100

             |                             |

             +--------------+--------------+

                            |

                            v

                    Observability EC2

                           |

                   +--------+--------+

                   |                 |

             Prometheus :9090   Node Exporter :9100

                   |

             +-----+------+

             |            |

             v            v

          Grafana     Alertmanager

          :3000          :9093

                            |

                            v

                        PagerDuty

                            |

                            v

                    Incident Notification

