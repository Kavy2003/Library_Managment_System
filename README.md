# Library_Managment_System
The Library Management System API is a web service developed using Flask, designed to manage books and members efficiently. It allows users to perform key operations such as adding, retrieving, updating, and deleting records for both books and members. To ensure security, the API employs token-based authentication.

## Overview
This project demonstrates the implementation of a Library Management System API using Flask. It supports managing books and members within a library, enabling CRUD operations for both entities. The API is equipped with essential features like token-based authentication, search capabilities, pagination, and secure access control.

---

## Key Features

### **Books Management**
- Add new books to the collection.
- Retrieve a list of all books.
- Fetch details for a specific book using its ID.
- Update book information.
- Remove books from the collection.
- Search for books by title or author with case-insensitive functionality.
- Implement pagination to retrieve books in manageable chunks.

### **Members Management**
- Add new library members.
- View a complete list of members.
- Get detailed information about a specific member by their ID.
- Update member details.
- Delete member records.

### **Authentication**
- Secure API endpoints using token-based authentication.
- Only requests with the correct token (`alpha beta gamma`) are granted access.

---

## Technologies Used
- **Flask**: Python micro-framework for creating the API.
- **Python**: Programming language used for development.

---

## Setup Instructions

### 1. Clone the Repository
Download the project to your local system:
```bash
git clone https://github.com/Kavy2003/Library_Managment_System

```
### 2. Install Dependencies
Set up the required environment:

Create a Virtual Environment (optional but recommended):
```bash
python -m venv venv

```
Activate the Environment:
On Windows:
```
.\venv\Scripts\activate
```
On MacOS/Linux:
```
source venv/bin/activate
```
Install Flask:
```
pip install flask
```
### 3. Run the Application
Execute the following command to launch the server:

```
python LMS.py
```
The API will be accessible at http://127.0.0.1:5000/.

### 4. API Authentication
API Endpoints
Books
POST /books: Add a new book.
Example request body:

```
{
  "title": "Book Title",
  "author": "Author Name",
  "isbn": "5389765434",
  "year": 2012
}
```
GET /books: Retrieve a list of books, with optional search and pagination.
Query parameters: search, page, per_page.
Example request: GET /books?search=Harry&page=1&per_page=5
GET /books/{book_id}: Fetch details for a specific book.
PUT /books/{book_id}: Update book information.
DELETE /books/{book_id}: Remove a book.
Members
POST /members: Add a new member.
Example request body:
```
{
  "name": "John Doe",
  "email": "johndoe@example.com"
}
```
GET /members: Retrieve a list of all members.
GET /members/{member_id}: Get details of a specific member.
PUT /members/{member_id}: Update a member's information.
DELETE /members/{member_id}: Remove a member.

### Authentication
Include the Authorization header with the token:

makefile
```
Authorization: alpha beta gamma
```

###Design Choices
Data Storage
The project uses in-memory storage for simplicity. For production, a persistent database (e.g., MySQL, PostgreSQL) is recommended.
Authentication
A static token (alpha beta gamma) is used for demonstration purposes. Secure mechanisms such as JWT or OAuth2 should be implemented in real-world scenarios.
Search and Pagination
Case-insensitive search is supported for book titles and authors.
Pagination ensures efficient data retrieval by limiting the number of records per request.
Error Handling
Returns meaningful error messages (e.g., 404 Not Found) for invalid or missing resources.

### Assumptions and Limitations
## Assumptions
Request bodies for adding or updating resources are correctly formatted JSON.
The token is consistently provided for every request.
All data is stored temporarily and will reset upon server restart.
## Limitations
Data Persistence: No database is integrated; data is lost when the server stops.
Authentication: The token-based approach is basic and lacks production-level security.
Advanced Features: No user roles or permissions are implemented.
Limited Search: Only supports searching by title or author.

### Tests
Use tools like Postman or curl to verify the functionality of the API.

Books
Add, retrieve, update, and delete books.
Test search and pagination features.
Members
Add, retrieve, update, and delete members.
