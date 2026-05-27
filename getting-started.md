# Getting Started

This guide shows developers how to make their first request to the EHR Patient API.

---

## Before You Begin

Before using the API, make sure you have:

- A registered healthcare application
- OAuth 2.0 client credentials
- Patient authorization
- Approved SMART on FHIR scopes
- Permission to access protected health information (PHI)

---

## Step 1: Register Your Application

Developers must register their application with the EHR platform before requesting patient data.

During registration, applications receive:

- Client ID
- Redirect URI
- Approved scopes

---

## Step 2: Request Authorization

The application redirects the patient to authorize access to their health data.

Example scopes:

```text
patient/Appointment.read
patient/MedicationRequest.read
patient/Observation.read
patient/Communication.write
```

---

## Step 3: Receive an Access Token

After authorization, the application receives an OAuth 2.0 access token.

```text
Authorization: Bearer ACCESS_TOKEN
```

---

## Step 4: Make Your First Request

Example request:

```bash
curl -X GET https://api.ehrportal.com/v1/appointments \
-H "Authorization: Bearer ACCESS_TOKEN"
```

---

## Step 5: Review the Response

Example response:

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
    }
  ]
}
```

---

## Privacy Notice

This API may return protected health information (PHI). Developers should request only the minimum necessary data, protect access tokens, and follow privacy and security requirements when handling patient information.

---

## Next Steps

Review the endpoint documentation:

- [GET /appointments](endpoints/appointments.md)
- [GET /medications](endpoints/medications.md)
- [GET /lab-results](endpoints/lab-results.md)
- [POST /messages](endpoints/messages.md)
