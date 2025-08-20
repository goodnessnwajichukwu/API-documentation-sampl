# 🎬 MovieHub REST API Documentation 

**Version:** v1.0  
**Last Updated:** August 19, 2025  
**Author:** Goodness Nwajichukwu – Technical Writer  

---

## 📖 Overview  
The **MovieHub REST API** allows developers to access movie data such as details, categories, and trending content. With this API, you can:  
- Search for movies by title  
- Retrieve movie details by ID  
- Get trending and popular movies  
- Explore categories/genres  

**Base URL:**

https://api.moviehub.io/v1

---

## 🔐 Authentication  
The API uses **API Key Authentication**.  

Include your API key in the header:

Authorization: Api-Key {your_api_key}

API keys can be generated from the developer dashboard and expire after 90 days.  

---

## 📊 Rate Limits  
- Free Tier: **60 requests/minute**  
- Pro Tier: **500 requests/minute**  

Response headers include:  
- `X-RateLimit-Limit`  
- `X-RateLimit-Remaining`  
- `X-RateLimit-Reset`  

---

## 🎥 Endpoints  

### 🔹 Get All Movies  
**Endpoint:** `GET /movies`  

**Request:**  
```bash
curl -X GET "https://api.moviehub.io/v1/movies" \
  -H "Authorization: Api-Key your_api_key"

Response:

{
  "movies": [
    {
      "id": "201",
      "title": "Echoes of Time",
      "year": 2023,
      "genre": "Drama",
      "rating": 8.5
    }
  ]
}


---

🔹 Search Movies by Title

Endpoint: GET /movies/search?title={query}

Request:

curl -X GET "https://api.moviehub.io/v1/movies/search?title=Inception" \
  -H "Authorization: Api-Key your_api_key"

Response:

{
  "id": "202",
  "title": "Inception",
  "year": 2010,
  "genre": "Sci-Fi",
  "rating": 9.0
}


---

🔹 Get Movie by ID

Endpoint: GET /movies/{id}

Request:

curl -X GET "https://api.moviehub.io/v1/movies/201" \
  -H "Authorization: Api-Key your_api_key"


---

🔹 Get Categories/Genres

Endpoint: GET /categories

Response:

{
  "categories": ["Action", "Drama", "Comedy", "Horror", "Sci-Fi"]
}


---

🔹 Get Trending Movies

Endpoint: GET /movies/trending

Response:

{
  "trending": [
    {
      "id": "210",
      "title": "The Last Horizon",
      "year": 2025,
      "rating": 9.3
    }
  ]
}


---

⚠️ Error Handling

Status Code	Meaning	Example Response

400	Bad Request (invalid data)	{ "error": "Invalid request" }
401	Unauthorized (no API key)	{ "error": "Missing or invalid API key" }
404	Not Found (invalid ID)	{ "error": "Movie not found" }
429	Too Many Requests	{ "error": "Rate limit exceeded" }
500	Internal Server Error	{ "error": "Something went wrong" }



---

📝 Best Practices & Precautions

Always use HTTPS for secure API calls.

Cache results where possible to reduce repeated requests.

Respect rate limits to avoid throttling.

Use proper error handling in your app.



---

❓ FAQs

Q: Do I need to pay to use the API?
A: The API has both free and pro tiers.

Q: How long does an API key last?
A: API keys expire after 90 days.

Q: Can I use this API for commercial apps?
A: Yes, but only with the Pro Tier.


---

🕒 Changelog

v1.0 (Aug 19, 2025) – Initial release with movies, categories, trending, and search endpoints.
