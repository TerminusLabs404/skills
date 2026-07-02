---
name: terminus-entity-formation
description: Form an LLC, C-Corp, or S-Corp in any US state. Get filing fees, step-by-step checklists, and required documents. Filed through CorpNet partnership.
tags: [formation, llc, incorporation, business, legal]
---

# Terminus Entity Formation

Form an LLC, C-Corp, or S-Corp in any US state. Get filing fees, step-by-step checklists, and required documents.

## Endpoints

### POST https://terminuslabs.fun/api/bankr-skill/formation

Form a business entity in any US state.

#### Input

```json
{
  "entity_type": "llc",
  "state": "DE",
  "name": "MyStartup"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| entity_type | string | yes | llc, c-corp, or s-corp |
| state | string | yes | 2-letter state code |
| name | string | no | Proposed business name for availability check |

#### Output

```json
{
  "ok": true,
  "skill": "terminus.formation",
  "entity_type": "llc",
  "state": "DE",
  "formation": {
    "filing_fee": 90,
    "checklist": [
      "Choose a unique business name",
      "Designate a registered agent",
      "File Articles of Organization with state SOS",
      "Draft operating agreement",
      "Obtain EIN from IRS",
      "Open business bank account",
      "Obtain necessary business licenses",
      "Register for state and local taxes"
    ]
  },
  "name_check": {
    "name": "MyStartup",
    "available": true
  },
  "next_step": "https://terminuslabs.fun/forge?type=llc&state=DE",
  "partner": "corpnet"
}
```

### GET https://terminuslabs.fun/api/bankr-skill

Returns the skill manifest with all available capabilities and input schemas.

## Supported Entity Types

| Type | Description |
|------|-------------|
| LLC | Limited Liability Company — most popular for startups and small businesses |
| C-Corp | C-Corporation — required for VC funding, stock options, IPO path |
| S-Corp | S-Corporation — pass-through taxation, limited to 100 shareholders |

All 50 states + DC supported. Filing fees vary by state ($50–$500).

## Examples

- "Form an LLC in Texas"
- "Start a C-Corp in Delaware"
- "How much does it cost to incorporate in California?"
- "Check if the name TechVentures is available in New York"
- "S-Corp formation in Florida"

## About

Terminus is the intelligence platform for cities, capital, and the agentic economy. FORGE is one of five AI agents — it handles entity formation across all 50 states + DC, filed through our CorpNet partnership. Business banking inline via Bridge (Stripe).

[terminuslabs.fun](https://terminuslabs.fun)
