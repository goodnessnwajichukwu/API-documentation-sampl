
# ![Banner](https://i.pinimg.com/736x/3T/FF/zo/3TFfzOZnX.jpg)  
# 📚 BookVault API Documentation  

**Version:** v1.0  
**Last Updated:** August 18, 2025  
**Author:** Goodness Nwajichukwu – Technical Writer  

---

## 📖 Overview  
The **BookVault REST API** allows developers to build applications that can manage books, authors, and categories.  
- Add new books  
- Retrieve book information  
- Update book details  
- Delete books  

**Base URL:**

https://api.bookvault.io/v1

---

## ![Authentication](https://i.pinimg.com/736x/1G/Q9/Mi/1GQ9MiqIc.jpg) Authentication  

The API uses **Bearer Token Authentication (JWT)**.  

Include your token in the header:

Authorization: Bearer {your_token}

---

## ![Rate Limits](https://i.pinimg.com/736x/3u/IK/ID/3uIKIDPfZ.jpg) Rate Limits  

- Free Tier: **100 requests/minute**  
- Pro Tier: **500 requests/minute**  
- Responses include headers:  
  - `X-RateLimit-Limit`  
  - `X-RateLimit-Remaining`  
  - `X-RateLimit-Reset`  

---

## ![Endpoints](https://i.pinimg.com/736x/3D/6Z/TJ/3D6ZTJooj.jpg) Endpoints  

### 🔹 Get All Books  
**Endpoint:** `GET /books`  

```bash
curl -X GET "https://api.bookvault.io/v1/books" \
  -H "Authorization: Bearer your_token"

Response:

{
  "books": [
    {
      "id": "101",
      "title": "The Silent Observer",
      "author": "Jane Doe",
      "published_year": 2022
    }
  ]
}


---

🔹 Add a New Book

Endpoint: POST /books

curl -X POST "https://api/bookvault.io/v1/books" \
  -H "Authorization: Bearer your_token" \
  -H "Content-Type: application/json" \
  -d '{
        "title": "Whispers of Tomorrow",
        "author": "John Smith",
        "published_year": 2025
      }'

Response:

{
  "id": "102",
  "title": "Whispers of Tomorrow",
  "author": "John Smith",
  "published_year": 2025,
  "status": "created"
}


---

 Example Code Snippet

💻 You can test endpoints using curl, Postman, or integrate with any programming language that supports HTTP requests.


---

📝 Notes

All requests must be sent via HTTPS

Use proper headers for JSON (Content-Type: application/json)

Handle rate limits gracefully in your application

