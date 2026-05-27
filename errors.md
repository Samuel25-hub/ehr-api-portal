# Error Handling

The EHR Patient API uses standard HTTP status codes and healthcare-specific error messaging to communicate request failures.

---

## Common Error Codes

| Status Code | Meaning |
|---|---|
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Consent Required or Access Restricted |
| 404 | Resource Not Found |
| 429 | Too Many Requests |
| 500 | Internal Server Error |

---

## Example Error Response

```json
{
  "error": "Consent Required",
  "message": "Patient consent is required before accessing lab results."
}
```

---

## Healthcare-Specific Error Scenarios

### Consent Required

Occurs when patient authorization is required before data can be accessed.

```json
{
  "error": "Consent Required",
  "message": "Patient consent must be verified before accessing this resource."
}
```

---

### Restricted Clinical Data

Occurs when sensitive healthcare data has restricted visibility.

```json
{
  "error": "Access Restricted",
  "message": "You do not have permission to access this clinical resource."
}
```

---

### Expired Access Token

Occurs when the OAuth access token has expired.

```json
{
  "error": "Unauthorized",
  "message": "Access token has expired."
}
```

---

## Security Recommendations

- Do not expose sensitive error details to end users.
- Log authentication and authorization failures securely.
- Avoid transmitting protected health information (PHI) in error responses.
- Follow organizational privacy and compliance policies when handling healthcare data.
