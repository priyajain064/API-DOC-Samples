# API Reference: Issue Card Endpoint

This document provides detailed reference for the `POST /cards/issue` endpoint.

## Endpoint

```
POST /cards/issue
```

## Description

Creates a new virtual or physical card linked to a user account.

## Authentication

Requires Bearer Token in header.

## Request

```json
{
  "user_id": "user_002",
  "type": "virtual",
  "spend_limit": 20000,
  "currency": "CAD"
}
```

### Parameters

| Name        | Type   | Required | Description                        |
|-------------|--------|----------|------------------------------------|
| user_id     | string | Yes      | The user to assign the card to     |
| type        | string | Yes      | 'virtual' or 'physical'            |
| spend_limit | int    | No       | Optional spend limit in cents      |
| currency    | string | Yes      | Currency code (e.g., CAD)          |

## Response

```json
{
  "card_id": "card_12345",
  "status": "active",
  "last4": "1234",
  "created_at": "2025-06-30T12:00:00Z"
}
```

## Errors

- 400 Bad Request
- 401 Unauthorized
