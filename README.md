
# GrimorioLab Oracle (Competitor Agent)

Deployed on Vercel. Provides `/api/competitors/analyze` for Figma Make.

## Quickstart
1. `npm i`
2. Copy `.env.example` to `.env` and fill:
   - SERVER_TOKEN=**strong-token**
   - OPENAI_API_KEY=sk-...
   - CORS_ORIGIN=*
   - MOCK=1 (set to 0 in prod)
3. `vercel dev` (or `vercel --prod`)

## Request
POST /api/competitors/analyze (Authorization: Bearer SERVER_TOKEN)

Body example:
```json
{
  "project_id": "demo-123",
  "brand": "Blauw GrimorioLab",
  "market": "Brand & Digital Design Studios",
  "region": "Canada",
  "languages": ["en","pt-br"],
  "briefing": { "mission": "Human brands that transform" },
  "competitors": ["Studio A","Studio B"],
  "tasks": ["market_scan","social_trends","visual_cues","archetype_match"],
  "mask_brand": true
}
```

## Response
Strict JSON with: summary, competitor_matrix, social_trends, visual_cues, risks, actions.

## Security
Never expose API keys in Figma Make. Use SERVER_TOKEN header; the server talks to the model.

© Blauw GrimorioLab — 2025-10-08
