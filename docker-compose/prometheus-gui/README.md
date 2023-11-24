# Prometheus with Grafana

Promethius has an api that allows it to gather details from diffrent sources

This is intended for development environments. Would need to be improved for production.

Will install the Prometheus server and agent on the same stack.
This will report back the node_exporter every 5s

## Prometheus

<http://localhost:9090/targets>

Should be all set up with the data coming in from the `prometheus/node-exporter` container

The `config/prometheus.yaml` config file has any 'scrapes' that are used and what endpoints receive the data

> alter the `config/prometheus.yaml` file and restart the container `docker compose up -d promethius`

## Graphana

### Setup

http://localhost:4000

login with admin:admin - then change your password

### Add data source

`Connections`->`Data Sources` <http://localhost:4000/connections/datasources/new> 

You can visualise any data available in the Grafana connections. The data from these 'agents' will be correctly processed by Grafana from their native formats.

Add the existing Prometheus data source from `Connections`->`Data Sources` <http://localhost:4000/connections/datasources/new> 

### Dashboards

<http://localhost:4000/dashboards>

> Set up the `Prometheus 2.0 Overview` dashboard from <https://grafana.com/grafana/dashboards/3662-prometheus-2-0-overview/>

Add any exisitng grafana.com dashboard by copying the dashboard id ( eg: 3662 ) and pasting it into your Grafana UI

`Dashboards`->`Import`->[paste in URL or ID]->`Load`  - Done :)

I have also created a stupidly simple dashboard. Import `config/uptime-dashboard.json` as above.


