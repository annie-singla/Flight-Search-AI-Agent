# Flight-Search-AI-Agent
FastAPI-powered AI agent integrating SerpAPI and LangChain to search and parse live flight data from SERPs. Supports natural language queries for routes, dates, and prices, returning structured results. Extensible master-agent design for adding hotel search, itineraries, or travel insights

An AI-powered multi-tool master agent built with FastAPI, LangChain, Azure OpenAI, and SerpAPI to search and parse real-time flight data from Google Flights search results.
Also supports dummy tools for integration testing (profile fetch, email writer, meeting scheduler, Slack notifier).

🚀 Features
🔍 Natural Language Flight Search
Example:
Flights from Delhi to London on August 30 return Sept 10
🌐 SerpAPI Integration – Fetches real-time data from Google Flights.

🧠 LangChain Master Agent – LLM-driven reasoning to decide which tool to use.

⚡ FastAPI REST API – Easy to integrate into any web or mobile app.

🔌 Extensible Tools – Add more agents for different business functions.

🛠 Tech Stack
Python

FastAPI – API backend

LangChain – Agent orchestration

Azure OpenAI – LLM reasoning

SerpAPI – Real-time flight search data

Requests + Regex + Datetime – Parsing and fetching results

📦 Installation

git clone https://github.com/yourusername/fastapi-flight-master-agent.git
cd fastapi-flight-master-agent
pip install -r requirements.txt
⚙ Configuration
Update your keys in the script:
AZURE_OPENAI_KEY = "your_azure_key"
AZURE_OPENAI_ENDPOINT = "your_azure_endpoint"
DEPLOYMENT_NAME = "your_deployment"
SERPAPI_KEY = "your_serpapi_key"
▶ Running the API

uvicorn main:app --reload --port 8000
📡 API Endpoints
1️⃣ Master Agent Endpoint
POST /agent
Request:

{
  "query": "Schedule a meeting and then find flights from Delhi to Paris on Sept 5 return Sept 12"
}
Response:
{
  "response": "✈️ Flights from DEL to CDG on 2025-09-05..."
}
2️⃣ Direct Flight Search Endpoint
POST /search-flights
Request:
{
  "query": "Flights from Bangalore to Tokyo on October 10 return October 20"
}
Response:
{
  "result": "✈️ Flights from BLR to NRT on 2025-10-10..."
}
📄 Example Output
✈️ Flights from DEL to LHR on 2025-08-30:

• British Airways | $650 | 480 mins
   - Indira Gandhi Intl (08:50) → Heathrow (13:50)

• Air India | $620 | 475 mins
   - Indira Gandhi Intl (02:00) → Heathrow (06:55)
