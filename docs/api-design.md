# API Design

## Create User

### Endpoint
POST /api/v1/users

### Request Payload
{
  "firstName": "mikasa",
  "lastName": "1234",
  "email": "mikasa@example.com"
}

### Create User Preferences

### Endpoint
POST /v1/users/{userId}/preferences

### Request Payload
{
  "travelStyle": [
    "food",
    "culture"
  ],
  "budget": "MEDIUM",
  "tripDuration": 7,
  "interests": [
    "museums",
    "local cuisine"
  ]
}

## Generate Personalized Itinerary

### Endpoint
POST /v1/itineraries

### Request Payload
{
  "user_id": "user_42",
  "trip_id": "trip_123",
  "constraints": {
    "avoid_crowds": true,
    "max_daily_activities": 4
  }
}