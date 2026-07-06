# API Design

## Create / update user (also stores user preferences)
Endpoints: 
POST /v1/users
PUT  /v1/users/{user_id}

Request:
{
  "travel_style": {
    "nature_vs_nightlife": 0.8,
    "luxury_vs_budget": 0.3,
    "pace": "relaxed"
  },
  "dietary_preferences": ["vegetarian"],
  "mobility_constraints": ["no_long_hikes"],
  "interests": ["history", "local food"]
}

## Create a trip
Endpoint : POST /v1/trips

Request:
{
  "destination": "Japan",
  "start_date": "2026-03-10",
  "end_date": "2026-03-20",
  "travelers": 2,
  "budget": "medium"
}

Response:
{ "trip_id": "trip_123" }

## Generate Personalized Itinerary
Endpoint: POST /v1/itineraries
Request:
{
  "user_id": "user_42",
  "trip_id": "trip_123",
  "constraints": {
    "avoid_crowds": true,
    "max_daily_activities": 4
  }
}