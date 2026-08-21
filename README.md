# Concert-Travel-Agent
A conversational agent that combines live concert data, real time flight pricing, and setlist information to help music fans plan concert travel without manually cross-referencing Ticketmaster, flight search engines, and setlist websites.


## What It Does
Given an artist and a departure city, the assistant:

1. Fetches real upcoming concert dates and official ticket links
2. Calculates round-trip flight prices to each venue
3. Checks recent setlists for specific songs if requested
4. Ranks results by best travel option (local shows prioritized, then cheapest flight)
5. Recommends similar touring artists if no upcoming shows are found


## Conversation Example
**Prompt:** `"bts concerts, I live in Dublin"`

The assistant returns upcoming BTS shows in Europe in or around Dublin with official Ticketmaster ticket links, round-trip flight prices from Dublin, airline, duration, and Google Flights links


## Tech Stack
- OpenAI Responses API
- Python
- Ticketmaster API, SerpAPI, Setlist.fm API, Last.fm API
- OpenAI Vector Store (RAG)
  

## External APIs
5 API keys required to run the agent:

TICKETMASTER_API_KEY

SERPAPI_KEY 

SETLIST_API_KEY 

LASTFM_KEY 

OPENAI_API_KEY 


| API | Purpose |
|---|---|
| Ticketmaster | Concert dates and venues |
| SerpAPI | Real time flight prices and booking links |
| Setlist.fm | Recent setlists |
| Last.fm | Similar artist graph (live fallback + RAG source) |


## Limitations
- **Airport coverage**: the airport code dictionary misses some smaller cities meaning concerts in uncovered cities are skipped rather than mapped to the nearest airport
- **RAG coverage**: the vector store covers ~100 artists which is sufficient for popular acts, but not niche ones


## Future Development
- Expand the RAG dataset (musically and geographically)
- Add nearest airport fallback for uncovered cities
- Integrate hotel pricing for total trip cost estimates
