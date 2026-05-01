# Market Digest Data Schema

Each hourly cron run appends an entry to `_data/digests/YYYY-MM-DD.json`.

## Schema

```json
{
  "time": "10:26 AM EDT",
  "date": "2026-05-01",
  "canadian_markets": [
    {
      "title": "BoC Holds at 2.25%, Warns of Consecutive Hikes if Oil Stays High",
      "url": "https://www.cbc.ca/news/...",
      "source": "CBC",
      "date": "Apr 29, 2026",
      "summary": "The Bank of Canada held...",
      "tags": ["BoC", "rates", "inflation"]
    }
  ],
  "us_global_markets": [
    { "title": "...", "url": "...", "source": "...", "date": "...", "summary": "...", "tags": [...] }
  ],
  "prediction_markets": [
    { "market": "BoC Rate Hike in 2026", "yes_pct": "68.5%", "no_pct": "31.5%", "delta": "+1.0%" }
  ],
  "market_snapshot": {
    "sp_tsx": { "value": "33,964", "direction": "up", "change": "+1.94%" },
    "sp_500": { "value": "7,272", "direction": "up", "change": "New 52w high" },
    "cad_usd": { "value": "0.737", "direction": "neutral", "change": "Stable" },
    "wti_crude": { "value": "~$105/bbl", "direction": "up", "change": "Multi-week high" },
    "ten_year_yield": { "value": "4.39%", "direction": "down", "change": "-0.09%" }
  },
  "analysis": {
    "theme": "Markets are pricing in...",
    "cad_angle": "The loonie is holding steady...",
    "risk_factor": "If Iran-related oil disruptions...",
    "polymarket_signal": "The 83% probability of Powell departing..."
  },
  "scenarios": {
    "short_term": [
      { "label": "Ceasefire / De-escalation", "probability": "47.0%", "detail": "Oil retraces ~$100-105", "impact": "CAD +0.5% · TSX Energy -3%", "sub_outcomes": [
        { "label": "Full diplomatic resolution", "conditional_prob": "30%", "impact": "Oil ~$95-100 · CAD +1% · TSX Energy -5%" }
      ]}
    ],
    "long_term": [
      { "label": "Zero rate cuts in 2026", "probability": "56.8%", "delta": "↓0.1%", "detail": "S&P range-bound · CAD under pressure" }
    ],
    "key_observation": "The market is caught between..."
  }
}
```
