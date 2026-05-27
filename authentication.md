# Authentication

The EHR Patient API uses OAuth 2.0 authorization with SMART on FHIR concepts to support secure access to patient health data.

---

## Authentication Method

Applications must request an access token before making API requests.

```text
Authorization: Bearer ACCESS_TOKEN
```

---

## Why Authentication Matters

This API handles sensitive patient health information. All requests must be authorized to help protect patient privacy, data security, and consent requirements.

---

## Example Authorization Header

```text
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI...
```

---

## Access Token Requirements

Access tokens should include appropriate scopes based on the type of patient data being requested.

Example scopes:

```text
patient/Appointment.read
patient/MedicationRequest.read
patient/Observation.read
patient/DocumentReference.read
```

---

## Security Notes

- Do not expose access tokens in public repositories.
- Do not store patient health information in client-side code.
- Only request the minimum data needed for the application.
- Follow privacy and security requirements when handling protected health information.
