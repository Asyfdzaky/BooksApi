# Books API

API ini merupakan bagian dari aplikasi Laravel yang menyediakan fitur CRUD untuk entitas **Books**. Dokumentasi ini menjelaskan endpoint, metode HTTP, dan respons yang tersedia.

## **Base URL**
`http://yourdomain/api/books`

---

## **Endpoints**

### **1. Get All Books**
- **Method**: `GET`
- **URL**: `/`
- **Description**: Mengambil daftar semua buku.
- **Response**:
  - **200 OK**:
    ```json
    {
        "message": "Success",
        "data": [
            {
                "id": 1,
                "title": "Book Title",
                "author": "Author Name",
                "published_at": "2024-01-01"
            }
        ]
    }
    ```
  - **500 Internal Server Error**:
    ```json
    {
        "message": "Error",
        "error": "Exception message"
    }
    ```

---

### **2. Get a Book by ID**
- **Method**: `GET`
- **URL**: `/{id}`
- **Description**: Mengambil detail buku berdasarkan ID.
- **Parameters**:
  - `id` (required): ID buku.
- **Response**:
  - **200 OK**:
    ```json
    {
        "message": "Books found",
        "data": {
            "id": 1,
            "title": "Book Title",
            "author": "Author Name",
            "published_at": "2024-01-01"
        }
    }
    ```
  - **404 Not Found**:
    ```json
    {
        "message": "Books not found"
    }
    ```
  - **500 Internal Server Error**:
    ```json
    {
        "message": "Error",
        "error": "Exception message"
    }
    ```

---

### **3. Create a New Book**
- **Method**: `POST`
- **URL**: `/`
- **Description**: Menambahkan buku baru ke database.
- **Request Body**:
  ```json
  {
      "title": "Book Title",
      "author": "Author Name",
      "published_at": "2024-01-01"
  }
