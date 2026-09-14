---
name: parse-coi
description: Extract a certificate of insurance (ACORD 25) into structured fields without running a compliance check, honoring the absent-vs-unreadable distinction.
api: Aervik Labs COI Verification
method: generated
generated: '2026-09-14'
source: openapi/aervik-labs-coi-verification.json
operations:
- parseCertificate
---

# Parse an ACORD 25 certificate into structured data

Use this skill when you only need the structured contents of a certificate, not
a pass/fail verdict. Base URL:
`https://certificate-of-insurance-verification-compliance-check-api.p.rapidapi.com`,
with `X-RapidAPI-Key` and `X-RapidAPI-Host` headers.

## Steps

1. **Extract the certificate** — `POST /parse` (`parseCertificate`). Provide the
   document as text, an uploaded file, or a file URL. The `ParseResponse` returns
   the `insurers` on the certificate, the coverage grids, and `other_coverages`.

## Rules to honor

- A blank field and an unreadable field are different answers: a value that is
  genuinely absent is returned as `null`; a value that is present but illegible
  is flagged with an `unreadable` `FieldStatus`. Never treat `unreadable` as
  absent.
- Supported inputs are validated: bad inputs return stable error codes such as
  `unsupported_mime_type`, `pdf_url_unsupported`, `invalid_file_url`,
  `unsupported_url_scheme`, or `input_too_large` (HTTP 413).
- `POST /parse` is a stateless, read-only extraction — safe to retry, nothing is
  persisted.
