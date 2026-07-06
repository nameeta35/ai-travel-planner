# AI-Travel-Planner Architecture

                 Client
                   |
                   v
          Spring Boot Travel API
                   |
                   |
        +----------+-----------+
        |                      |
        v                      v
 Preference Service       Itinerary Service
        |                      |
        |                      |
        +----------+-----------+
                   |
                   v
          Python AI Orchestration Service
                (Flask/FastAPI)
                   |
                   v
              MCP Layer
                   |
        +----------+-----------+
        |                      |
        v                      v
    LLM Provider          Travel Tools
                         (APIs/MCP Servers)
                              |
              +---------------+---------------+
              |               |               |
           Weather        Maps           Restaurants


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