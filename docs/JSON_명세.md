1. User
```json
{
  "user_id": "UUID",
  "email": "string",
  "password": "string",
  "name": "string",
  "nationality": "integer",
  "language": "string",
  "profile_photo": "string",
  "bio": "string",
  "residence": "string",
  "role": "string",
  "last_login_time": "string"
}
```

2. TravelPlan
```json
{
  "travel_id": "UUID",
  "user_id": "string",
  "destination": "string",
  "start_date": "string",
  "end_date": "string",
  "interests": "string",
  "status": "string"
}
```

3. Application
```json
{
  "application_id": "string",
  "status": "string",
  "user_id": "UUID",
  "related_id": "string"
}
```

4. Chat
```json
{
  "chat_id": "string",
  "user_id": "string",
  "message": "string",
  "timestamp": "string"
}
```

5. Review
```json
{
  "review_id": "string",
  "trip_id": "string",
  "reviewer_id": "string",
  "reviewee_id": "string",
  "rating": "integer",
  "content": "string",
  "timestamp": "string"
}
```

6. Inquiry
```json
{
  "inquiry_id": "string",
  "user_id": "string",
  "title": "string",
  "content": "string",
  "status": "string",
  "timestamp": "string"
}
```
