---
title: "Sanctions aliases and entity types, company recall searches, and AI replies cut off mid-answer"
url: "https://aerviklabs.com/changelog/#2026-09-15-sanctions-aliases-recalls-and-cut-off-replies"
date: "2026-09-15"
feed_url: "https://aerviklabs.com/changelog.xml"
---
US Import Risk Screening: the Consolidated Screening List section compared a supplier’s name only with each record’s listed name, so a name the list gives as an alias could match a different record instead (“IRISL” matched a vessel named IRIS rather than ISLAMIC REPUBLIC OF IRAN SHIPPING LINES, which lists IRISL as its alias). The listed name and every alias are now scored. Records the list itself types as an entity, vessel or aircraft were held back when their names were short enough to look like a person’s, so the screen could report no hits for “Sinaloa Cartel” or “Air Shiraz”; they are now
