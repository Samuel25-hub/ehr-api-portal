# GET /appointments

Retrieve upcoming and past patient appointment information.

---

## Endpoint

```text
GET /appointments
```

---

## Description

Returns a list of scheduled appointments associated with the authenticated patient account.

---

## Required Scope

```text
patient/Appointment.read
```

---

## Example Request

```bash
curl -X GET https://api.ehrportal.com/v1/appointments \
-H "Authorization: Bearer ACCESS_TOKEN"
```

---

## Example Response

```json
{
  "appointments": [
    {
      "appointment_id": "APT-1001",
      "provider": "Dr. Sarah Johnson",
      "department": "Cardiology",
      "date": "2026-06-10",
      "time": "09:30 AM",
      "location": "Houston Medical Center"
    },
    {
      "appointment_id": "APT-1002",
      "provider": "Dr. Michael Lee",
      "department": "Primary Care",
      "date": "2026-06-18",
      "time": "01:00 PM",
      "location": "Downtown Clinic"
    }
  ]
}
```

---

## Response Fields

| Field | Type | Description |
|---|---|---|
| appointment_id | string | Unique appointment identifier |
| provider | string | Healthcare provider name |
| department | string | Clinical department |
| date | string | Appointment date |
| time | string | Appointment time |
| location | string | Clinic or hospital location |

---

## Status Codes

| Code | Description |
|---|---|
| 200 | Successful request |
| 401 | Unauthorized |
| 403 | Consent required |
| 404 | Appointment data not found |

---

## Security Notes

Appointment data may contain protected health information (PHI). Applications should securely store and transmit patient appointment information according to organizational privacy and security policies.
