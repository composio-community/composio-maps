<img src="assets/logo.png" alt="Composio Maps logo" width="96">

# Composio Maps

Composio Maps brings Google Maps into Claude: find places by description or nearby coordinates, get opening hours, ratings and contact details, get directions with travel time by car, foot, bike or transit, and convert between addresses and coordinates.

Sign in with your Composio account; no Google account or API key is needed. It runs on Composio Instant tools; lookups are paid from your Composio wallet.

## What it can do

- Find places by text or near coordinates
- Opening hours, ratings, phone and website for a place
- Directions and travel time by car, foot, bike or transit
- Address to coordinates and back
- Place photos

## Install

**Claude (web, desktop, Cowork):** once the plugin is listed, add it from Customize > Plugins in Claude. To try it before then, download this repository as a zip and upload it from Customize > Plugins > Add > Upload plugin.

**Claude Code:**

```
/plugin install composio-maps --marketplace composio-community/composio-maps
```

Then connect the server: in Claude, open the plugin's **Connectors** tab and connect `composio-maps`; in Claude Code, run `/mcp` and authenticate `composio-maps`. Either way, you sign in with your Composio account. No Google Maps Platform account or API key is needed.

## Try asking

- "Find highly rated sushi near Union Square, San Francisco"
- "How long is the drive from Boston to Portland, Maine?"
- "What are the opening hours of the British Museum?"

## What's inside

| Skill | When Claude uses it |
|---|---|
| `find-places` | Use Composio Maps to find places by description or near coordinates, look up a place's opening hours and details, get directions and travel time, or convert between addresses and coordinates. |

The plugin adds one remote MCP server, `composio-maps`, at `https://connect.composio.dev/mcp/google_maps` (Composio Connect), and the skill tells Claude which of its tools to use and how. It runs no local code and installs no packages.

## Data and cost

- **What is sent:** the details of each lookup Claude makes, such as a search query, a place, a handle or a URL, go to Composio, which calls the Google Maps Platform API with Composio's credentials and returns the result to Claude. The plugin doesn't read your files, chat history or memory.
- **Sign-in:** OAuth with your Composio account.
- **Cost:** lookups run on Composio Instant tools and are paid from your Composio wallet.

## Privacy, terms and support

- Privacy policy: https://composio.dev/privacy
- Terms of service: https://composio.dev/terms
- Support: https://composio.dev/support
- Security reports: see [SECURITY.md](SECURITY.md)

## License

[MIT](LICENSE)
