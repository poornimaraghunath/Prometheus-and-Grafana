# Prometheus-and-Grafana

# Why monitoring is required ?
     Because to monitor the large number kubernetes cluster in this prometheus is used for monitoring the clusters and grafana is used for better visualization.

# Prometheus architecture   

  +------------------------+      +------------------------+
  |                        |      |                        |
  |     Monitored Targets |      |       Alertmanager     |
  |   (Applications,      |      |  (Handles alerts and   |
  |    Services, Servers) |<---->|   sends notifications)  |
  |                        |      |                        |
  +-----------+------------+      +------------+-----------+
              |                                |
              | HTTP Requests (metrics)        | Alerts
              |                                |
              v                                v
  +-----------+-----------+      +------------+------------+
  |                       |      |                         |
  |   Prometheus Server   |<---->|     Grafana            |
  | (Scrapes and stores   |      | (Visualization and     |
  |   metrics, executes   |      |  dashboarding tool)    |
  |   PromQL queries)     |      |                         |
  |                       |      |                         |
  +-----------------------+      +-------------------------+

   
   it is prometheus server in which it has components like

   # Http server - which is make an api request to the kubernetes api server to collect the metrics
   # TSDB - which is used to store the time when the metrics was collected.
   # Node - which is storgae it as HDD or ssd

   Monitored Targets:

These are the systems or applications that Prometheus monitors. They expose metrics via HTTP endpoints in a format Prometheus understands.
#Prometheus Server:Responsible for scraping and storing metrics data from the monitored targets. It periodically pulls metrics data from targets, stores them in its time-series database, and executes PromQL queries against the stored data for visualization and alerting.

#Alertmanager:Receives alerts generated by Prometheus based on predefined alerting rules. It handles alert grouping, deduplication, and notification routing to various integrations such as email, PagerDuty, Slack, etc.

#Grafana:Grafana is a separate component often used alongside Prometheus for visualization and dashboarding. It connects to Prometheus as a data source, allowing users to create rich, interactive dashboards to visualize metrics data collected by Prometheus.

#HTTP Requests (metrics):Prometheus retrieves metrics data from monitored targets by making HTTP requests to their designated endpoints. These endpoints expose metrics in a format understood by Prometheus, typically in a simple text-based format like Prometheus exposition format.

#Alerts:Alerts are generated by Prometheus based on predefined alerting rules. When certain conditions are met (e.g., threshold exceeded), Prometheus triggers alerts which are then forwarded to Alertmanager for further processing and notifications.
