# AI-Travel-Planner Architecture

  ├── User Service
  ├── Trip Context Service
  ├── Planning Orchestrator
  │     ├── Context Builder
  │     ├── Tool Router
  │     └── LLM
  └── Cache / In-memory store (Redis)

# System Workflow
1. Fetch user profile (DB → Redis cache)
2. Fetch trip context
3. Enrich with external data
   - Weather
   - Seasonality
   - Events
4. Build planning prompt
5. Call LLM
6. Post-process output
7. Return itinerary