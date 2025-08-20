# 📚 Book Vault REST API Documentation

Welcome to the **Book Vault REST API**.  
This API allows developers to manage books, authors, and categories with full CRUD operations.

---

# 🚀 Quick Start

1. **Sign Up & Get API Key**  
   - Register at [Book Vault Developer Portal](https://example.com/signup)  
   - Copy your **API key** from your dashboard  

2. **Make Your First Request**  
   Using `curl` in your terminal:  
   ```bash
   curl -H "Authorization: Bearer YOUR_API_KEY" \
   https://api.bookvault.com/books

3. Sample Response

[
  {
    "id": 1,
    "title": "The Silent Ocean",
    "author": "Jane Doe",
    "category": "Fiction"
  }
]



👉 Or explore endpoints instantly with our 📂 Postman Collection.

✅ In less than 5 minutes, you’ll have your first response running!


---

🔑 Authentication

All requests require an API key.
Pass it in the Authorization header as a Bearer token:

Authorization: Bearer YOUR_API_KEY


---

📖 Endpoints

📚 Books

GET /books → Retrieve all books

POST /books → Add a new book

GET /books/{id} → Get book details

PUT /books/{id} → Update book details

DELETE /books/{id} → Delete a book


✍️ Authors

GET /authors → Retrieve all authors

POST /authors → Add a new author


🏷️ Categories

GET /categories → Retrieve all categories

POST /categories → Add a new category



---

⏳ Rate Limit

100 requests/minute per API key

Exceeding the limit returns 429 Too Many Requests



---

❌ Error Handling

Code	Message	Meaning

400	Bad Request	Invalid input or missing parameters
401	Unauthorized	API key missing or invalid
404	Not Found	Resource does not exist
500	Server Error	Something went wrong on our side



---

⚡ Best Practices & Precautions

Always use HTTPS for secure requests

Implement caching to avoid hitting rate limits

Handle errors gracefully (retry on 500, backoff on 429)

Never expose your API key in public repos



---

❓ FAQs

Q: Do I need to pay to use the API?
A: Free tier available (1,000 requests/day). Paid plans unlock higher limits.

Q: Do you support GraphQL?
A: Currently REST only, GraphQL coming soon.


---

📝 Changelog

v1.0.0 → Initial release

v1.1.0 → Added categories endpoint

v1.2.0 → Improved error messages
