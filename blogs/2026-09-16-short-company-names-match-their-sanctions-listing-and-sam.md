---
title: "Short company names match their sanctions listing, and SAM.gov records carry their own provenance"
url: "https://aerviklabs.com/changelog/#2026-09-16-sanctions-name-forms-and-sam-provenance"
date: "2026-09-16"
feed_url: "https://aerviklabs.com/changelog.xml"
---
US Import Risk Screening: a company name written without its foreign legal form did not match the listing that carries one, so a search for “VVB” scored below the match threshold against the listed “VVB, PAO” and was counted only as incomplete coverage. Those forms (PAO, PJSC, OOO, OAO, ZAO, JSC, AD and similar) are now read where a legal form goes, so the short name matches its record. Names that differ in their substantive words still do not match.
