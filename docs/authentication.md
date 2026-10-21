# Authentication

All requests to the PulseMetrics API use API key authentication over HTTPS.

## Get an API key
1. Sign in to your PulseMetrics workspace.
2. Go to **Settings → API Keys → Create key**.
3. Copy the key immediately — it is shown only once.

## Use the key
Send the key in the `Authorization` header:

```bash
curl https://api.pulsemetrics.example/v1/metrics \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## Rate limits
| Plan | Requests per minute |
|---|---|
| Starter | 60 |
| Growth | 600 |
| Enterprise | 6,000 |

When you exceed the limit, the API returns `429 Too Many Requests` with a `Retry-After` header. See [Errors](errors.md).

**Warning:** Never embed an API key in client-side code or commit it to a public repository. Rotate keys from **Settings → API Keys** if one is exposed.
