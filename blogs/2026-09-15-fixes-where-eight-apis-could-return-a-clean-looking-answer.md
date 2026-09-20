---
title: "Fixes where eight APIs could return a clean-looking answer that was not complete"
url: "https://aerviklabs.com/changelog/#2026-09-15-fixes-where-apis-could-look-complete"
date: "2026-09-15"
feed_url: "https://aerviklabs.com/changelog.xml"
---
Landed Cost Estimator: the bundled U.S. tariff schedule was cut off in places (rate text at 40 characters, descriptions at 180) in the 2026-09-02 snapshot; it is replaced by a complete 2026-09-14 snapshot, and /health now reports tariff_schedule_snapshot . AD/CVD (anti-dumping and countervailing duty) exposure is now reported as not assessed for every origin: the per-origin lists behind “assessed” had no cited source.
