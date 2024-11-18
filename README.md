# Dokumentasi GDOC API 

API ini merupakan bagian dari aplikasi Laravel yang menyediakan fitur CRUD untuk entitas **Books**. Dokumentasi ini menjelaskan endpoint, metode HTTP, dan respons yang tersedia.

## **Base URL**
'http://127.0.0.1:8000/api/books'

---
## **Fitur**
- Mendapatkan daftar semua buku.
- Menambahkan buku baru.
- Mengambil detail buku berdasarkan ID.
- Memperbarui informasi buku.
- Menghapus buku berdasarkan ID.

## **Endpoints**

### **1. Get All Books**
- **Method**: `GET`
- **URL**: `URL  : http://127.0.0.1:8000/api/books`
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
- **URL**: `http://127.0.0.1:8000/api/books/{id}`
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
- **URL**: `http://127.0.0.1:8000/api/books`
- **Description**: Menambahkan buku baru ke database.
- **Request Body**:
  ```json
  {
      "title": "Book Title",
      "author": "Author Name",
      "published_at": "2024-01-01"
  }
   ```
  - **Response**:
  - **200 OK**:
    ```json
    {
    "message": "Book created successfully",
    "data": {
        "id": 1,
        "title": "Book Title",
        "author": "Author Name",
        "published_at": "2024-01-01"
    }
    ```
  - **422 Unprocessable Entity:**:
    ```json
    {
        "message": "Error",
        "error": "Validation error message"
    }
    ```
  - **500 Internal Server Error**:
    ```json
    {
        "message": "Error",
        "error": "Exception message"
    }
    ```
### **4. Update a Book**
- **Method**: `PUT/PATCH`
- **URL**: `http://127.0.0.1:8000/api/books/{id}`
- **Request Body**:
  ```json
  {
    "title": "Updated Title",
    "author": "Updated Author",
    "published_at": "2024-01-02"
    }
   ```
  - **Response**:
  - **200 OK**:
    ```json
    {
    "message": "Book updated successfully",
    "data": {
        "id": 1,
        "title": "Updated Title",
        "author": "Updated Author",
        "published_at": "2024-01-02"
    }
    }
    ```
  - **422 Unprocessable Entity:**:
    ```json
    {
        "message": "Error",
        "error": "Validation error message"
    }
    ```
  - **500 Internal Server Error**:
    ```json
    {
        "message": "Error",
        "error": "Exception message"
    }
    ```
### **5. Delete a Book**
- **Method**: `delete`
- **Description**: `Menghapus buku dari database`
- **URL**: `http://127.0.0.1:8000/api/books/{id}`
- **Request Body**:
  ```json
  {
    "title": "Updated Title",
    "author": "Updated Author",
    "published_at": "2024-01-02"
    }
   ```
  - **Response**:
  - **200 OK**:
    ```json
    {
    "message": "Book delete successfully",
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
    

