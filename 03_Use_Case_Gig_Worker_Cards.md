# Use Case: Creating Temporary Virtual Cards for Gig Workers

This guide explains how to create single-use virtual cards for gig workers to make controlled purchases (e.g., food delivery expenses).

## Workflow Overview

1. Authenticate using your API key
2. Create a virtual card
3. Apply spend control limits
4. Monitor usage or auto-disable after first use

## API Steps

### Step 1: Create Virtual Card

```json
POST /cards/issue

{
  "user_id": "driver_987",
  "type": "virtual",
  "currency": "CAD",
  "spend_limit": 4000,
  "metadata": {
    "one_time_use": true
  }
}
```

### Step 2: Set Controls

```json
POST /cards/controls

{
  "card_id": "card_45678",
  "merchant_types": ["grocery", "restaurant"],
  "expires_at": "2025-07-02T00:00:00Z"
}
```

### Step 3: Monitor & Revoke

```http
DELETE /cards/card_45678
```

## Benefits

- Secure, temporary card issuance
- Merchant and spend-specific limits
- Better fraud and spend control
