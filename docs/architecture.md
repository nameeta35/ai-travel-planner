# AI-Travel-Planner Architecture

## High-Level Architecture

```mermaid
flowchart LR
    Client[Client Applications]

    API[Spring Boot Travel API]

    User[User Service]
    Pref[Preference Service]
    Trip[Itinerary Service]

    AI[Python AI Orchestration Service]
    MCP[MCP Tool Layer]

    LLM[LLM Provider]

    Weather[Weather API]
    Maps[Maps API]
    Places[Places API]

    Client --> API

    API --> User
    API --> Pref
    API --> Trip

    Trip --> AI

    AI --> MCP

    MCP --> LLM
    MCP --> Weather
    MCP --> Maps
    MCP --> Places
```

# Python AI Service Workflow
1. Retrieve user preferences
2. Select tools
3. Call MCP servers
4. Build context
5. Call LLM
6. Return itinerary

# MCP tools
- get_weather(destination)
- search_attractions(location)
- find_restaurants(preferences)