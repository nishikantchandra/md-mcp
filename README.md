# Mahadasha.com — Vedic Astrology & Kundli MCP Server (`md-mcp`)

[![MCP Endpoint](https://img.shields.io/badge/MCP-Streamable%20HTTP-8B0000)](https://mahadasha.com/api/mcp)
[![Official Docs](https://img.shields.io/badge/Docs-mahadasha.com%2Fapi-blue)](https://mahadasha.com/api)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Official Model Context Protocol (MCP) server and client bridge for **[Mahadasha.com](https://mahadasha.com)** and **[Dasha Jyotish](https://mahadasha.com/api)** — an astronomical-grade Vedic astrology (Jyotish) calculation engine powered by **Swiss Ephemeris** and **Lahiri Ayanamsha** telemetry[cite: 10, 11].

This MCP connector grounds AI assistants (Claude, ChatGPT, Cursor, Windsurf, and Gemini in Chrome via WebMCP) in deterministic planetary math so they can compute exact Sidereal birth charts and Dasha timelines without hallucinating planetary degrees[cite: 11].

- **Live Remote MCP Endpoint:** `https://mahadasha.com/api/mcp`
- **API & Developer Portal:** [https://mahadasha.com/api](https://mahadasha.com/api)
- **Web Platform:** [https://mahadasha.com](https://mahadasha.com)

---

## Available MCP Tools

| Tool Name | Description | Key Inputs |
| :--- | :--- | :--- |
| `calculate_vedic_kundli` | Computes an exact Sidereal birth chart (D1 Kundli) with Ascendant (Lagna), Moon Sign (Rashi), Nakshatra Pada, and planetary degrees[cite: 10, 15]. | `birth_date`, `birth_time`, `latitude`, `longitude`, `timezone_offset` |
| `get_vimshottari_dasha` | Calculates active and upcoming 120-year Vimshottari Mahadasha and Antardasha periods with exact transition dates[cite: 11, 14]. | `birth_date`, `birth_time`, `latitude`, `longitude`, `timezone_offset` |
| `get_daily_panchang` | Returns daily Tithi, Nakshatra, Yoga, Karana, Rahu Kaal, and auspicious Muhurat windows for any location[cite: 10]. | `date`, `latitude`, `longitude`, `timezone_offset` |
| `get_navtara_tara_bala` | Evaluates the 9-Star Tara Bala compatibility and daily lunar transit favorability from the natal Moon Nakshatra[cite: 20]. | `natal_nakshatra`, `transit_date` |

---

## Quick Setup

### Option 1: Direct Remote URL (Claude Web, ChatGPT & WebMCP)
Add the hosted Streamable HTTP endpoint directly inside **Claude (`Customize → Connectors → Add Custom Connector`)** or any remote MCP client:

```text
[https://mahadasha.com/api/mcp](https://mahadasha.com/api/mcp)
```

### Option 2: Claude Desktop / Cursor / Windsurf (`mcp-remote` Bridge)
Add the following block to your `claude_desktop_config.json` or `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "mahadasha-vedic-astrology": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "[https://mahadasha.com/api/mcp](https://mahadasha.com/api/mcp)"
      ]
    }
  }
}
```

### Option 3: Claude Code CLI
```bash
claude mcp add --transport http mahadasha [https://mahadasha.com/api/mcp](https://mahadasha.com/api/mcp)
```

---

## Interactive Web Calculators & Resources

- [Vimshottari Dasha Calculator](https://mahadasha.com/vimshottari-dasha-calculator) — Full Mahadasha, Antardasha & Pratyantardasha timeline[cite: 11, 14]
