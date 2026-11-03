# AIclicks MCP

Track how ChatGPT, Perplexity, Gemini and Google AI Overviews mention and cite your brand.

AIclicks MCP is a hosted, remote [Model Context Protocol](https://modelcontextprotocol.io) server. Connect it to Claude, ChatGPT, Cursor or any MCP client and ask about your brand's AI visibility, competitors, citations and prompts in plain language.

- **Remote URL:** `https://mcp.aiclicks.io/mcp` (Streamable HTTP)
- **Website:** [aiclicks.io](https://aiclicks.io)

There's nothing to install. This repository holds the public listing only; the server is operated by AIclicks.

## Connect

### OAuth (recommended)

Add `https://mcp.aiclicks.io/mcp` as a custom connector in your MCP client and sign in with your AIclicks account.

### API key

Create an API key in the AIclicks app, then:

```json
{
  "mcpServers": {
    "aiclicks": {
      "url": "https://mcp.aiclicks.io/mcp",
      "headers": { "Authorization": "Bearer ak_live_..." }
    }
  }
}
```

Claude Code:

```sh
claude mcp add --transport http aiclicks https://mcp.aiclicks.io/mcp \
  --header "Authorization: Bearer ak_live_..."
```

## Tools

Most tools take a `domain_id`, which `list_domains` returns.

| Area | Tools |
|---|---|
| Account | `validate_key`, `list_domains`, `get_domain_status`, `get_team_usage` |
| Visibility | `get_visibility_time_series`, `get_mentions_time_series`, `get_brand_rankings`, `get_model_leaderboard` |
| Prompts | `list_prompts`, `list_prompt_metrics`, `get_prompt_statistics`, `get_prompt_brands`, `get_answers`, `list_fanout_queries` |
| Citations | `get_citations`, `get_citation_domains`, `get_citation_share`, `get_citations_time_series`, `get_citability_time_series` |
| Competitors | `list_competitors`, `get_competitor_time_series`, `get_competitor_citations`, `get_competitor_discovery` |
| Sentiment | `get_sentiment_overview`, `get_sentiment_time_series`, `list_sentiment_themes`, `get_sentiment_theme_sources`, `get_sentiment_answers` |
| Topics & tags | `list_topics`, `get_topic_metrics`, `list_tags`, `get_tag_metrics` |
| ChatGPT ads | `get_chatgpt_ads_kpis`, `get_chatgpt_ads_timeline`, `get_chatgpt_ads_leaderboard`, `get_chatgpt_ads_prompts`, `get_chatgpt_ads_cards` |
| Google Analytics 4 | `get_ga4_summary`, `get_ga4_timeline`, `get_ga4_by_llm`, `get_ga4_top_pages`, `get_ga4_top_locations`, `get_ga4_top_browsers`, `get_ga4_devices`, `get_ga4_key_events` |
| Recommendations | `list_engage_recommendations` |
| Write (Pro+ plans) | `add_prompt(s)`, `update_prompt`, `archive_prompts`, `add_competitor(s)`, `update_competitor`, `create_topic`, `create_tag`, `set_prompt_topics`, `set_prompt_tags`, `create_domain` |

## Example prompts

- "How has my brand's visibility in ChatGPT changed over the last 30 days?"
- "Which competitors outrank us on Perplexity, and which sources cite them?"
- "What are the top domains AI models cite when answering my prompts?"
- "Show sentiment themes for my brand this month."

## Support

[aiclicks.io](https://aiclicks.io)
