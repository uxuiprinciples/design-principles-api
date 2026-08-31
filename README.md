<div align="center">
  <a href="https://uxuiprinciples.com">
    <img src="https://uxuiprinciples.com/android-chrome-512x512.png" alt="UX/UI Principles" width="100">
  </a>
</div>

# UX/UI Principles API

Query 195 research-backed UX/UI principles, 8 UX smells and 5 flow checklists over HTTP, in English and Spanish.

Every principle carries a code from a six-part taxonomy, an academic basis, and a summary written to be pasted into Cursor, v0 or Claude.

**Full reference: [uxuiprinciples.com/en/docs/api](https://uxuiprinciples.com/en/docs/api)** — that page is the source of truth and is kept current. This README is the short version.

## Quick start

No key needed to try it. The free tier returns metadata for the sample principles:

```bash
curl "https://uxuiprinciples.com/api/v1/principles?slug=fitts-law"
```

```json
{
  "success": true,
  "data": {
    "slug": "fitts-law",
    "title": "Fitts's Law",
    "code": "I.2.2.02",
    "part": "part-4",
    "partName": "Part IV - Interface Patterns",
    "difficulty": "intermediate",
    "readTime": 14,
    "aiSummary": "Fitts's Law (Fitts 1954, MacKenzie 1992) demonstrates movement time follows MT = a + b × log₂(2D/W), with larger closer targets reducing interaction time 40-60%...",
    "tags": ["motor-performance", "target-acquisition", "touch-targets"]
  },
  "meta": { "version": "v1", "tier": "free", "locale": "en" }
}
```

With a key, send it as a bearer token:

```bash
curl -H "Authorization: Bearer $UXUI_API_KEY" \
  "https://uxuiprinciples.com/api/v1/principles?part=part-6"
```

## Endpoints

Base URL is `https://uxuiprinciples.com/api/v1`.

| Endpoint | Method | Access | Returns |
|---|---|---|---|
| `/principles` | GET | free, enriched with a key | Filter by `slug`, `part`, `difficulty`, `search`, `locale`, `limit`. `include_content=true` needs a key. |
| `/smells` | GET | key required | The 8 UX antipatterns with fix recipes. Filter by `id` or `category`. |
| `/flows` | GET | key required | The 5 pre and post-flight checklists. Filter by `id`. |
| `/audit` | POST | key required | Match an interface description against the taxonomy. |
| `/validate` | POST | key required | Validate a design against a chosen set of principles. |

Without a key, `/smells` and `/flows` answer `403`. That is the tier boundary, not an error in your request.

## The taxonomy

Principle codes carry their part: `F.` Foundations, `C.` Core Principles, `D.` Design Systems, `I.` Interface Patterns, `S.` Specialized, `H.` Human-Centered.

| Part | Domain | Principles |
|---|---|---|
| Part 1 | Foundations | 32 |
| Part 2 | Core Principles | 34 |
| Part 3 | Design Systems | 22 |
| Part 4 | Interface Patterns | 23 |
| Part 5 | AI-Native and Specialized | 61 |
| Part 6 | Human-Centered Excellence | 23 |

## Access

| Tier | What you get | Price |
|---|---|---|
| Free | Metadata for the sample principles, no key needed | $0 |
| API Access | All 195 principles with full content, smells, flows, audit and validate. 1,000 requests/hour | $19/year |

[Get a key →](https://uxuiprinciples.com/en/checkout)

## Other ways in

- **MCP server.** [`@uxuiprinciples/mcp-server`](https://www.npmjs.com/package/@uxuiprinciples/mcp-server) puts the same data in Claude Desktop and Claude Code. Free, no key required.
- **Agent skills.** [uxuiprinciples/agent-skills](https://github.com/uxuiprinciples/agent-skills) is five SKILL.md files for Cursor, Windsurf and kx. Free.

## License

The API is a hosted service; this repository holds documentation only. Principle text is proprietary and stays behind the Principles Library.
