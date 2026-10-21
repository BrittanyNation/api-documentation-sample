# Errors

PulseMetrics uses conventional HTTP status codes and one error body format everywhere:

```json
{
  "error": {
    "code": "metric_not_found",
    "message": "No metric exists with id met_9999.",
    "request_id": "req_8f42c1"
  }
}
```

## Error catalog
| HTTP status | Code | Meaning | Fix |
|---|---|---|---|
| 400 | `invalid_request` | A parameter failed validation | Check the field named in `message` |
| 401 | `unauthorized` | Missing or invalid API key | Send a valid key in the `Authorization` header |
| 403 | `forbidden` | Key lacks permission for this resource | Use a key with the required scope |
| 404 | `metric_not_found` | The resource does not exist | Verify the ID |
| 429 | `rate_limited` | Too many requests | Wait for the `Retry-After` interval |
| 500 | `internal_error` | Something failed on our side | Retry with backoff; quote the `request_id` in support tickets |
