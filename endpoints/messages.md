# POST /messages

Send secure messages between patients and healthcare providers.

---

## Endpoint

```text
POST /messages
```

---

## Description

Allows authenticated patients to securely send messages to healthcare providers through the patient portal messaging system.

---

## Required Scope

```text
patient/Communication.write
```

---

## Request Headers

| Header | Value |
|---|---|
| Authorization | Bearer ACCESS_TOKEN |
| Content-Type | application/json |

---

## Example Request Body

```json
{
  "provider_id": "PROV-1001",
  "subject": "Prescription Refill Request",
  "message": "I would like to request a refill for my blood pressure medication."
}
```

---

## Example Request

```bash
curl -X POST https://api.ehrportal.com/v1/messages \
-H "Authorization: Bearer ACCESS_TOKEN" \
-H "Content-Type: application/json"
```

---

## Example Response

```json
{
  "message_id": "MSG-1001",
  "status": "Sent",
  "timestamp": "2026-05-26T14:30:00Z"
}
```

---

## Response Fields

| Field | Type | Description |
|---|---|---|
| message_id | string | Unique message identifier |
| status | string | Delivery status |
| timestamp | string | Message submission timestamp |

---

## Status Codes

| Code | Description |
|---|---|
| 201 | Message sent successfully |
| 400 | Invalid request |
| 401 | Unauthorized |
| 403 | Consent required |

---

## Security Notes

Secure messages may contain protected health information (PHI). Applications should encrypt message data during transmission and storage and follow organizational privacy and compliance requirements.
