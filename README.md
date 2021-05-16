# REST API Gateway Cloudwatch Logs AWS Service Integration Example

This template configures a REST API Gateway AWS service integration directly to CloudWatch Logs.

This is a basic example with no authentication required. In the real world, you probably want to set that up.

## Expected Input

You must `POST` a JSON object to the `/logs` endpoint e.g.

```
{
    "message": "test",
    "timestamp": 1621155747562
}
```

The timestamp must be in milliseconds since the UNIX epoch. See https://currentmillis.com/.

## Testing

Example test using `Curl` against the API stage e.g.

```
curl -d "{\"message\":\"test log\", \"timestamp\":$(date +%s%3N)}" -H "Content-Type: application/json" -X POST https://xxxxxx.execute-api.eu-west-2.amazonaws.com/Test/logs
```
