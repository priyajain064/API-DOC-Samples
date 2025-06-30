# Getting Started with the Payments API

This quickstart guide walks you through how to authenticate and make your first payment request using our RESTful Payments API.

## Authentication

You’ll need a valid API key and token. All API requests must include the following header:

```
Authorization: Bearer YOUR_API_KEY
```

## Base URL

```
https://api.example.com/d1
```

## Making Your First Payment Request

### Endpoint

```
POST /payments
```

### Sample Request

```json
{
  "amount": 4300,
  "currency": "USD",
  "recipient_id": "user_123",
  "description": "Payment for May delivery"
}
```

### Sample cURL

```bash
curl -X POST https://api.example.com/d1/payments \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{ "amount": 4300, "currency": "USD", "recipient_id": "user_123" }'
```

### Sample Response

```json
{
  "payment_id": "pay_456789",
  "status": "processing",
  "created_at": "2025-05-26T12:00:00Z"
}
```

## Error Handling

| Code | Meaning            | Resolution                |
|------|--------------------|---------------------------|
| 401  | Unauthorized       | Check your API key        |
| 400  | Bad Request        | Check JSON structure      |
