---
title: "COI Verification: an unread policy date is never reported missing"
url: "https://aerviklabs.com/changelog/#2026-09-15-coi-policy-dates-and-workers-comp"
date: "2026-09-15"
feed_url: "https://aerviklabs.com/changelog.xml"
---
COI Verification: a policy date the reading left empty without saying it could not read the cell was reported as missing from the certificate, which turned an illegible expiration date into a coverage deficiency (seen on 1 of 3 live calls on the same certificate, 2026-09-15). A policy date missing from a coverage row the certificate shows is now withheld as not established from the certificate, and a requirement that depends on it returns cannot_determine . Blank limits and unmarked checkboxes are still reported as absent.
