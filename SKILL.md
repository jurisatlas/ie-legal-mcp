---
name: ie-legal-mcp-skill
description: Official Ireland (IE) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Ireland Legal Research & Multi-Tier Case Law Skill (`ie-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Ireland (IE)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `[2024] IESC 10 or [2024] IECA 45`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** District Court of Ireland, Circuit Court of Ireland & High Court of Ireland (IEHC)
   - **Second Instance (Cantonal / Regional / Appellate):** Court of Appeal of Ireland (IECA — Civil & Criminal)
   - **Supreme & Constitutional Instance:** Supreme Court of Ireland / Cúirt Uachtarach na hÉireann (IESC)
   - **Primary Tiered Database:** Courts Service of Ireland Judgments Registry (courts.ie/judgments — IEHC, IECA, IESC) (`https://www.courts.ie/judgments`)
