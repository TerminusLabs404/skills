---
name: terminus-grant-discovery
description: Search 2,800+ grant programs across grants.gov, SAM.gov, 50 state databases, and EU Funding & Tenders. Returns matching programs with titles, agencies, deadlines, and verification links.
tags: [grants, funding, government, nonprofit, startup]
---

# Terminus Grant Discovery

Search 2,800+ federal, state, and EU grant programs across 21 sectors. Get program titles, agencies, deadlines, and verification links.

## Endpoints

### POST https://terminuslabs.fun/api/bankr-skill/grants

Search grant programs by keyword, state, entity type, or sector.

#### Input

```json
{
  "query": "clean energy grants for nonprofits",
  "state": "CA",
  "entity_type": "501c3",
  "sectors": "energy, environment"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| query | string | yes | Natural language query (e.g. "AI research funding", "small business grants in Texas") |
| state | string | no | 2-letter state code — filters to state-eligible + national programs |
| entity_type | string | no | for_profit, 501c3, 501c4, sole_prop, government, academic |
| sectors | string | no | Comma-separated sectors from available list |

Abbreviations auto-expand: AI, EV, STEM, SBIR, DOD, DOE, HHS, EPA, USDA, NSF, NIH, HBCU, IoT, R&D.

#### Output

```json
{
  "ok": true,
  "skill": "terminus.grant-discovery",
  "query": "clean energy grants for nonprofits",
  "preview": [
    {
      "title": "Clean Energy Manufacturing Innovation Institute",
      "agency": "Department of Energy",
      "deadline": "2026-09-30",
      "verify": "https://www.grants.gov/search-results-detail/123456",
      "source": "grants.gov"
    }
  ],
  "total": 28,
  "sources": ["grants.gov", "CA state programs", "EU Funding & Tenders (SEDIA)"]
}
```

### GET https://terminuslabs.fun/api/bankr-skill

Returns the full skill manifest with available sectors, abbreviation expansions, and input schemas.

## Available Sectors (21)

health (1,084), education (189), research (189), defense (173), international (160), public_safety (69), natural_resources (57), agriculture (44), technology (43), legal (39), disaster_relief (30), business (30), housing (29), community_development (29), transportation (19), energy (12), clean_energy (10), workforce (12), environment (2), finance (6), social_services (2)

## Data Coverage

- 1,905 active federal programs (grants.gov, synced every 6 hours)
- 255 state programs across 50 states + DC (synced every 12 hours)
- 630 active EU programs (Horizon Europe, Erasmus+, LIFE, Digital Europe)
- SAM.gov entity lookup and contract opportunities (live)

## Examples

- "Find grants for AI startups in Georgia"
- "SBIR funding for biotech companies"
- "Clean energy grants for nonprofits in California"
- "STEM education funding"
- "Small business grants in Texas"
- "NIH health research grants"
- "HUD housing programs in New York"
- "USDA agriculture grants"

## About

Terminus is the intelligence platform for cities, capital, and the agentic economy. FIAT is one of five AI agents — it handles grant discovery, eligibility scoring, and application drafting across federal, state, and EU programs.

Free preview shows top 5 programs ranked by relevance with verification links. Full access includes eligibility scores, match percentages, deadline alerts, and AI-drafted application narratives.

[terminuslabs.fun](https://terminuslabs.fun)
