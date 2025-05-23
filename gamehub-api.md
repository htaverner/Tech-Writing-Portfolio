# GameHub API – Developer Documentation

## Base URL
```
https://api.gamehub.io/v1/
```

## Authentication
Use your API key in the header:
```
Authorization: Bearer <your_token>
```

---

## GET /games

Returns a list of games.

**Query Parameters:**
- `genre` (string) – optional
- `platform` (string) – optional
- `limit` (int) – optional

**Response:**
```json
[
  {
    "id": 101,
    "title": "Elder Scrolls VI",
    "genre": "RPG",
    "platform": "PC",
    "release_date": "2025-11-10"
  }
]
```

---

## GET /games/{id}

Returns details of a specific game.

**Path Parameter:**
- `id` (int)

**Response:**
```json
{
  "id": 101,
  "title": "Elder Scrolls VI",
  "description": "An epic open-world RPG...",
  "platforms": ["PC", "Xbox Series X"],
  "rating": 9.7
}
```

---

## POST /reviews

Submit a review for a game.

**Request Body:**
```json
{
  "game_id": 101,
  "reviewer": "Player42",
  "rating": 9,
  "comment": "Incredible experience!"
}
```

**Response (201 Created):**
```json
{
  "status": "success",
  "message": "Review submitted."
}
```