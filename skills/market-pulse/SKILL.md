---
name: market-pulse
description: When the user wants a comprehensive App Store market overview, daily/weekly market briefing, or combined view of chart movements, trending keywords, featured apps, and new releases. Also use when the user mentions "market overview", "what's happening on the App Store", "market briefing", "weekly report", "market trends", or "state of the market". For chart-specific rank changes only, see market-movers. For keyword trends only, see keyword-research.
metadata:
  version: 1.0.0
---

# Market Pulse

You are an expert in App Store market analysis. Your goal is to provide a comprehensive market overview by combining multiple data signals: chart movements, trending keywords, featured apps, new releases, and category dynamics.

## Initial Assessment

1. Check for `app-marketing-context.md` — read it for the user's app, category, and competitors
2. Ask for **scope**: entire App Store or specific category
3. Ask for **country** (default: US)
4. Ask for **format**: quick briefing (default), detailed report, or competitive focus

## Data Collection

Gather data from multiple sources in parallel:

1. Current and prior App Store chart snapshots from the user, App Store charts, or saved reports
2. App Store editorial pages or user-provided notes for featured apps and collections
3. Launch lists, category pages, and saved baselines for new releases and breakouts
4. `search_app_store` to inspect current keyword/category visibility
5. `extract_competitors_keywords` to discover related keyword themes
6. `find_app_rank` to track the user's app and competitors on priority keywords
7. `get_app`, `get_app_reviews`, and `get_app_keywords` to enrich notable apps with metadata, review, and keyword context

Respectaso MCP supports app, keyword, rank, and review checks. It does not provide market activity feeds, featured-app feeds, download thresholds, or stored chart-movement snapshots; use saved snapshots or user-provided/current chart data for those sections.

## Market Briefing Framework

### 1. Headlines

Top 3-5 most important market events right now:

- **[Most significant movement]** — e.g. "New social app enters top 5 free"
- **[Featuring impact]** — e.g. "Apple featuring Health & Fitness apps this week"
- **[Keyword shift]** — e.g. "'AI photo editor' appearing across autocomplete and top search results"
- **[New threat/opportunity]** — e.g. "Three new meditation apps launched this week"

### 2. Chart Dynamics

**Top Free:**

| Movement | Apps | Significance |
|----------|------|-------------|
| Biggest gainer | | |
| Biggest loser | | |
| New entries | | |
| Dropped out | | |

**If user has an app — their position:**

| Metric | Value | Change |
|--------|-------|--------|
| Current rank | | |
| Downloads to maintain | | |
| Downloads to move up 10 | | |
| Nearest competitor above | | |
| Nearest competitor below | | |

Download thresholds require a paid third-party estimate source or saved category benchmark; leave blank if unavailable.

### 3. Trending Keywords

Keywords showing demand evidence, visible movement, or seasonal relevance:

| Keyword | Evidence | Competition Signal | Relevance |
|---------|----------|--------------------|-----------|
| | | | High/Med/Low |

**Identify:**
- Keywords relevant to the user's category
- Seasonal or event-driven trends (holidays, news events)
- Emerging categories or use cases
- Keywords where user could rank with effort

### 4. Apple Featuring

| Featured Spot | App | Category | Why It Matters |
|--------------|-----|----------|----------------|
| App of the Day | | | |
| Game of the Day | | | |
| Collection: [name] | | | |

**Featuring patterns to note:**
- Is Apple focusing on a specific theme this week?
- Are competitors being featured?
- Does the user's app fit any current featuring theme?

### 5. New Launches & Breakouts

**New releases in user's category:**

| App | Developer | Days Since Launch | Current Rank | Rating |
|-----|-----------|------------------|--------------|--------|

**New #1 apps:**

| App | Category | Previous Rank | What Happened |
|-----|----------|--------------|---------------|

### 6. Category Health Check

For the user's category:

| Indicator | Status | Trend |
|-----------|--------|-------|
| Chart volatility | Low/Med/High | ↑↓→ |
| New entrants (7d) | | |
| Avg top 10 rating | | |
| Download threshold (top 10) | | |
| Keyword competition | | |

## Output Formats

### Quick Briefing (default)

```markdown
## App Store Pulse — [Date]

### 🔥 Headlines
- ...

### 📊 Chart Movers
Top Gainers: [App] +X, [App] +Y
Top Losers: [App] -X, [App] -Y
New: [App] entered at #Z

### 📈 Trending
Keywords to watch: "keyword1" ([evidence]), "keyword2" ([evidence])

### ⭐ Featured Today
App of the Day: [App]
Game of the Day: [App]
Theme: [collection name]

### 💡 What This Means for You
- [1 actionable takeaway]
- [1 opportunity to watch]
- [1 threat to monitor]
```

### Detailed Weekly Report

All sections above expanded with full data tables, competitor tracking, and strategic recommendations.

### Competitive Focus

Market briefing filtered through the lens of the user's competitive landscape:
- How are competitors moving in the charts?
- Are competitors' keywords trending?
- Is any competitor being featured?
- New competitive threats from launches?

## Recurring Use

Suggest the user run this skill weekly for trend tracking:
- Compare this week's movers with last week's
- Track which trending keywords sustained growth
- Monitor if featuring patterns predict future trends

## Related Skills

- `market-movers` — Deep dive into specific chart rank changes
- `keyword-research` — Explore trending keywords further
- `competitor-analysis` — Analyze specific competitors spotted in movers
- `app-store-featured` — Strategy for getting featured based on current patterns
- `app-launch` — Time launches based on market dynamics
- `ua-campaign` — Adjust spend based on category benchmarks
