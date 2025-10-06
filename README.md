# Prometheus-tips


#### Test Alert manager
```
curl -XPOST http://localhost:9093/api/v2/alerts \
  -H 'Content-Type: application/json' \
  -d '[
    {
      "labels": {
        "alertname": "TestAlert",
        "severity": "critical"
      },
      "annotations": {
        "summary": "resolve test alert"
      },
      "startsAt": "'$(date -u +%Y-%m-%dT%H:%M:%SZ)'",
      "endsAt": "'$(date -u -d '+1 minute' +%Y-%m-%dT%H:%M:%SZ)'"
    }
  ]'
```
