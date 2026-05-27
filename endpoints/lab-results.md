# GET /lab-results

Retrieve patient laboratory test results.

---

## Endpoint

```text
GET /lab-results
```

---

## Description

Returns lab result records associated with the authenticated patient account, including test names, result values, reference ranges, and result status.

---

## Required Scope

```text
patient/Observation.read
```

---

## Example Request

```bash
curl -X GET https://api.ehrportal.com/v1/lab-results \
-H "Authorization: Bearer ACCESS_TOKEN"
```

---

## Example Response

```json
{
  "lab_results": [
    {
      "result_id": "LAB-1001",
      "test_name": "Hemoglobin A1C",
      "value": "6.1",
      "unit": "%",
      "reference_range": "4.0-5.6",
      "status": "High",
      "date": "2026-05-15"
    }
  ]
}
```

---

## Response Fields

| Field | Type | Description |
|---|---|---|
| result_id | string | Unique lab result identifier |
| test_name | string | Name of the lab test |
| value | string | Reported result value |
| unit | string | Unit of measurement |
| reference_range | string | Expected normal range |
| status | string | Result status |
| date | string | Date result was reported |

---

## Status Codes

| Code | Description |
|---|---|
| 200 | Successful request |
| 401 | Unauthorized |
| 403 | Consent required |
| 404 | Lab result data not found |

---

## Security Notes

Lab results may contain protected health information (PHI). Applications should display and store lab data securely and follow privacy requirements for patient health information.
