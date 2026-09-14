---
name: verify-coi-compliance
description: Extract an ACORD 25 certificate of insurance and check it against your coverage requirements, returning a three-state verdict that distinguishes a deficient value from one that could not be read.
api: Aervik Labs COI Verification
method: generated
generated: '2026-09-14'
source: openapi/aervik-labs-coi-verification.json
operations:
- createRequirementsProfile
- verifyCertificate
- getRequirementsProfile
---

# Verify a Certificate of Insurance against your requirements

Use this skill to automate ACORD 25 vendor-onboarding checks. Base URL:
`https://certificate-of-insurance-verification-compliance-check-api.p.rapidapi.com`.
Every request needs the `X-RapidAPI-Key` and `X-RapidAPI-Host` headers.

## Steps

1. **(Optional, reusable) Save a requirements profile** — `POST /requirements`
   (`createRequirementsProfile`). Send a `RequirementsProfile` describing the
   `general_liability`, `auto_liability`, `umbrella_excess` and `workers_comp`
   limits your contract demands. The response returns an `id` you can reuse.

2. **Verify a certificate** — `POST /verify` (`verifyCertificate`). Provide the
   certificate (document text, an uploaded file, or a file URL) plus either an
   inline `requirements` object or the saved profile. The `VerifyResult`
   contains a `verdict` (`compliant` / `deficient` / `cannot_determine`), a list
   of `deficiencies` (each with a `FieldStatus` that flags `unreadable` fields),
   and the `parsed` `CoiData`.

3. **Re-fetch a saved profile** — `GET /requirements/{id}`
   (`getRequirementsProfile`) when you need to inspect the rules a check ran
   against.

## Rules to honor

- A `cannot_determine` verdict or an `unreadable` field status is NOT a pass and
  NOT a fail — the value was on the document but could not be read; route it to a
  human. The API withholds unquoted values (returns `null`) rather than guessing.
- Errors use a `{ error, message }` envelope where `error` is a stable code
  (e.g. `unsupported_mime_type`, `invalid_file_url`, `requirements_not_found`).
  See errors/aervik-labs-problem-types.yml.
- There is no idempotency key; do not blindly retry `POST /requirements` on a
  network error or you may create duplicate profiles.
- RapidAPI enforces the monthly quota (50 free / 150 PRO / 750 ULTRA / 3000 MEGA)
  and answers rate-limit failures in its own format.
