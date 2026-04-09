# ChatGPT Fan-Out Query Extractor

A browser bookmarklet that extracts the behind-the-scenes search queries ("fan-out queries") that ChatGPT makes when performing web searches. Works with GPT 5.3 and 5.4.

## Why?

When ChatGPT triggers a web search, it generates multiple search queries internally to gather information. Understanding these queries gives SEOs and AI researchers insight into how ChatGPT interprets prompts and what terminology it uses when searching the web.

## Installation

1. Copy the entire contents of [`bookmarklet.js`](bookmarklet.js)
2. Create a new bookmark in your browser
3. Paste the code as the bookmark URL
4. Name it something like "ChatGPT Queries"

## Usage

1. Open a ChatGPT conversation that triggered a **web search**
2. Click the bookmarklet
3. A new tab opens listing all fan-out queries from that conversation
4. Click **Copy All** to copy them to your clipboard

## How it works

The bookmarklet calls ChatGPT's internal `/backend-api/conversation/{id}` endpoint using your active session and recursively extracts all values found under `search_model_queries` and `search_queries` keys, regardless of nesting depth.

## Requirements

- You must be logged in to ChatGPT in the same browser
- The conversation must have triggered web search (look for the "Searched X sites" indicator)

## Credits

Fan-out query discovery in 5.3/5.4 by [Klaas Foppen](https://www.linkedin.com/in/klaasfoppen/) and [Gijs de Groot](https://www.linkedin.com/in/gijsdegroot/) from [Promptwatch](https://promptwatch.io/).

## License

MIT
