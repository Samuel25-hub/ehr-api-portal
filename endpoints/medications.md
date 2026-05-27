# GET /medications

Retrieve active and past patient medication records.

---

## Endpoint

```text
GET /medications
```

---

## Description

Returns medication information associated with the authenticated patient account, including active prescriptions and medication history.

---

## Required Scope

```text
patient/MedicationRequest.read
```

---

## Example Request

```bash
curl -X GET https://api.ehrportal.com/v1/medications \
-H "Authorization: Bearer ACCESS_TOKEN"
```

---

## Example Response

```json
{
  "medications": [
    {
      "medication_id": "MED-1001",
      "name": "Lisinopril",
      "dosage": "10 mg",
      "frequency": "Once daily",
      "status": "Active"
    },
    {
      "medication_id": "MED-1002",
      "name": "Metformin",
      "dosage": "500 mg",
      "frequency": "Twice daily",
      "status": "Active"
    }
  ]
}
```

---

## Response Fields

| Field | Type | Description |
|---|---|---|
| medication_id | string | Unique medication identifier |
| name | string | Medication name |
| dosage | string | Prescribed dosage |
| frequency | string | Medication schedule |
| status | string | Medication status |

---

## Status Codes

| Code | Description |
|---|---|
| 200 | Successful request |
| 401 | Unauthorized |
| 403 | Consent required |
| 404 | Medication data not found |

---

## Security Notes

Medication data may contain protected health information (PHI). Applications should securely manage medication records and follow healthcare privacy and security standards.
