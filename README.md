# EHR Patient API Documentation

Developer-focused healthcare API documentation portal built using Markdown, GitHub, and GitHub Pages.

This project demonstrates healthcare-focused REST API documentation, SMART on FHIR authentication workflows, patient data access patterns, HIPAA-aware documentation practices, and clinical information architecture.

---

## Quick Links

- [Authentication](authentication.md)
- [Getting Started](getting-started.md)
- [Error Handling](errors.md)

### Clinical Endpoints
- Appointments
- Medications
- Lab Results
- Secure Messaging

---

## Overview

The EHR Patient API allows authorized healthcare applications to securely retrieve patient health information including appointments, medications, lab results, and secure provider messaging data.

This project is modeled after modern healthcare interoperability systems such as Epic MyChart and SMART on FHIR-based APIs.

---

## API Workflow

Patient Application  
↓  
OAuth 2.0 Authentication  
↓  
SMART on FHIR Authorization  
↓  
EHR Patient API  
↓  
Clinical Database  
↓  
FHIR JSON Response

---

## Base URL

```text
https://api.ehrportal.com/v1
```

---

## Standards Used

- REST API
- SMART on FHIR
- OAuth 2.0
- JSON
- HIPAA-aware documentation practices

---

## Response Format

All responses are returned in JSON format using FHIR-compatible resource structures.
