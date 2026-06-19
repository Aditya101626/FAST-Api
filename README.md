# FAST-Api 🚀

A FastAPI-based CRUD application demonstrating REST API development with Python, Pydantic validation, and in-memory data storage.

## Overview

This project showcases a modern approach to building robust REST APIs using FastAPI. It implements complete CRUD (Create, Read, Update, Delete) operations with proper data validation, error handling, and interactive API documentation.

## ✨ Features

- **FastAPI Framework**: Built with FastAPI for high performance and automatic API documentation
- **CRUD Operations**: Complete Create, Read, Update, and Delete functionality
- **Data Validation**: Pydantic models for robust input validation and serialization
- **In-Memory Storage**: Efficient data storage for demonstration purposes
- **Interactive Documentation**: Auto-generated Swagger UI and ReDoc documentation
- **Type Hints**: Full type annotations for better code quality and IDE support
- **Error Handling**: Comprehensive error handling with appropriate HTTP status codes
- **CORS Support**: Cross-Origin Resource Sharing enabled for client applications

## 🛠️ Tech Stack

- **Backend Framework**: [FastAPI](https://fastapi.tiangolo.com/)
- **Data Validation**: [Pydantic](https://pydantic-settings.readthedocs.io/)
- **Server**: [Uvicorn](https://www.uvicorn.org/)
- **Language**: Python 3.7+

## 📋 Prerequisites

Before you begin, ensure you have:
- Python 3.7 or higher installed
- pip (Python package installer)
- Virtual environment (recommended)

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Aditya101626/FAST-Api.git
cd FAST-Api
```

### 2. Create a Virtual Environment

```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
uvicorn main:app --reload
```

The API will be available at `http://localhost:8000`

## 📚 API Documentation

Once the application is running, access the interactive documentation:

- **Swagger UI**: [http://localhost:8000/docs](http://localhost:8000/docs)
- **ReDoc**: [http://localhost:8000/redoc](http://localhost:8000/redoc)

## 🔌 API Endpoints

### Create
- **POST** `/items/` - Create a new item
  ```json
  {
    "name": "Item Name",
    "description": "Item Description",
    "price": 29.99
  }
  ```

### Read
- **GET** `/items/` - Get all items
- **GET** `/items/{item_id}` - Get a specific item

### Update
- **PUT** `/items/{item_id}` - Update an item
  ```json
  {
    "name": "Updated Name",
    "description": "Updated Description",
    "price": 39.99
  }
  ```

### Delete
- **DELETE** `/items/{item_id}` - Delete an item

## 📁 Project Structure

```
FAST-Api/
├── main.py              # Main application entry point
├── models.py            # Pydantic data models
├── requirements.txt     # Project dependencies
└── README.md           # This file
```

## 💡 Example Usage

### Using Python Requests

```python
import requests

BASE_URL = "http://localhost:8000"

# Create an item
response = requests.post(f"{BASE_URL}/items/", json={
    "name": "Laptop",
    "description": "High-performance laptop",
    "price": 999.99
})
print(response.json())

# Get all items
response = requests.get(f"{BASE_URL}/items/")
print(response.json())

# Get a specific item
response = requests.get(f"{BASE_URL}/items/1")
print(response.json())

# Update an item
response = requests.put(f"{BASE_URL}/items/1", json={
    "name": "Updated Laptop",
    "description": "Very high-performance laptop",
    "price": 1199.99
})
print(response.json())

# Delete an item
response = requests.delete(f"{BASE_URL}/items/1")
print(response.status_code)
```

### Using cURL

```bash
# Create an item
curl -X POST "http://localhost:8000/items/" \
  -H "Content-Type: application/json" \
  -d '{"name":"Laptop","description":"High-performance laptop","price":999.99}'

# Get all items
curl -X GET "http://localhost:8000/items/"

# Get a specific item
curl -X GET "http://localhost:8000/items/1"

# Update an item
curl -X PUT "http://localhost:8000/items/1" \
  -H "Content-Type: application/json" \
  -d '{"name":"Updated Laptop","description":"Very high-performance laptop","price":1199.99}'

# Delete an item
curl -X DELETE "http://localhost:8000/items/1"
```

## 📦 Requirements

Create a `requirements.txt` file with:

```
fastapi==0.104.1
uvicorn[standard]==0.24.0
pydantic==2.5.0
python-multipart==0.0.6
```

## 🔐 Security Considerations

- This project uses in-memory storage, so data is lost on restart
- For production use, implement a proper database
- Add authentication and authorization mechanisms
- Implement rate limiting to prevent abuse
- Use HTTPS in production environments

## 🧪 Testing

You can test the API endpoints using:
- **Swagger UI**: Interactive testing in the browser
- **cURL**: Command-line testing
- **Postman**: Advanced API testing tool
- **Python requests**: Programmatic testing

## 📈 Future Enhancements

- [ ] Database integration (PostgreSQL, MongoDB)
- [ ] User authentication and authorization
- [ ] API rate limiting
- [ ] Request logging and monitoring
- [ ] Unit and integration tests
- [ ] Docker containerization
- [ ] Deployment guides (Heroku, AWS, GCP)
- [ ] API versioning

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the MIT License - see the LICENSE file for details.

## 📧 Contact

For questions or suggestions, feel free to reach out:
- GitHub: [@Aditya101626](https://github.com/Aditya101626)

## 🙏 Acknowledgments

- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [Pydantic Documentation](https://docs.pydantic.dev/)
- [Uvicorn Documentation](https://www.uvicorn.org/)

---

**Happy Coding!** 🎉 If you found this project helpful, please consider giving it a star ⭐
