# Endpoints

Base URL: `https://api.pulsemetrics.example/v1`

## Metrics

### List metrics
`GET /metrics`

| Parameter | Type | Required | Description |
|---|---|---|---|
| `service` | string | No | Filter by service name |
| `from` | string (ISO 8601) | No | Start of the time range |
| `to` | string (ISO 8601) | No | End of the time range |

Example response:
```json
{
  "data": [
    {"id": "met_1024", "service": "checkout", "name": "latency_p95", "value": 212, "unit": "ms"}
  ]
}
```

### Create a metric alert
`POST /alerts`

| Field | Type | Required | Description |
|---|---|---|---|
| `metric_id` | string | Yes | Metric to watch |
| `threshold` | number | Yes | Value that triggers the alert |
| `channel` | string | Yes | `email`, `slack`, or `webhook` |

Returns `201 Created` with the new alert object.

## Dashboards

### Get a dashboard
`GET /dashboards/{id}` — returns the dashboard definition, including panels and their metric queries.
