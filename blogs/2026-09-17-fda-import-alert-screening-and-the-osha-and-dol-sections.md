---
title: "FDA Import Alert Screening and the OSHA and DOL sections now screen organizations only, and say when they withheld a record"
url: "https://aerviklabs.com/changelog/#2026-09-17-organizations-only-fda-and-epa"
date: "2026-09-17"
feed_url: "https://aerviklabs.com/changelog.xml"
---
FDA Import Alert Screening: some firms on FDA’s Import Alert lists are sole proprietors listed under a person’s name. An entry whose listed name may identify an individual is no longer returned. When one would have matched, the response sets withheld_possible_individual and incomplete_coverage to true and carries a coverage_note pointing to FDA’s own lists, so a no_match with incomplete_coverage: true is not a clean result.
