# UX/UI Principles API

Access 168 research-backed design principles programmatically.

## Overview

Each principle includes:
- Clear definition
- Academic citations (2,098+ total)
- AI-ready prompts for Cursor, V0, Claude
- Related principles

## Quick Start

```bash
curl https://api.uxuiprinciples.com/v1/principles/fitts-law
```

```json
{
  "id": "fitts-law",
  "name": "Fitts's Law",
  "definition": "The time to acquire a target is a function of the distance to and size of the target.",
  "citations": ["Fitts, P.M. (1954)"],
  "category": "interaction",
  "prompt": "Ensure interactive elements are large enough and positioned to minimize movement distance..."
}
```

## Categories

- `foundations` — Core principles (Fitts's Law, Hick's Law, etc.)
- `visual` — Color, typography, hierarchy
- `interaction` — Touch targets, feedback, affordances
- `accessibility` — WCAG compliance
- `cognitive` — Mental models, memory, attention

## Pricing

| Tier | Requests | Price |
|------|----------|-------|
| Free | 100/month | $0 |
| Pro | Unlimited | $29/year |

## Full Documentation

[View all 168 principles →](https://uxuiprinciples.com)

[API Documentation →](https://api.uxuiprinciples.com/docs)

## License

API access requires subscription. Principle definitions are proprietary.
