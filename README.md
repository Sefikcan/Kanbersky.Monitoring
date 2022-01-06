# Kanbersky.Monitoring
  This project was created to test metric tools in .net 6.

# Project Article-TR
https://sefikcankanber.medium.com/grafana-ve-prometheus-kullanarak-asp-net-core-projelerini-nas%C4%B1l-monit%C3%B6r-edebiliriz-f6a0777336e9

# Project Notes - EN
- Prometheus is an open-source monitoring application. It scrapes HTTP endpoints to collect metrics exposed in a simple text format.
- For example, your web app might expose a metric like
```
http_server_requests_seconds_count{exception="None", method="GET",outcome="SUCCESS",status="200",uri="api/v1/hc"} 123
```
which means that the endpoint /api/v1/hc was successfully queried 123 times via a GET request.
- Prometheus can also create alerts if a metric exceeds a threshold, e.g. if your endpoint returned more than one-hundred times the status code 500 in the last 5 minutes.
- To set up Prometheus, we create three files:
  - prometheus/prometheus.yml — the actual Prometheus configuration
  - prometheus/alert.yml — alerts you want Prometheus to check
  - docker-compose.yml
# TODO: keep adding notes


# TODO:
- Slack integration
