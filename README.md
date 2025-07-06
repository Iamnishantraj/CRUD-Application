# Book CRUD Application

A simple CRUD (Create, Read, Update, Delete) application for books using Node.js, Express.js, MongoDB, and Mongoose.

## Features

- Create new books
- Read all books
- Read a specific book by ID
- Update book information
- Delete books

## Prerequisites

- Node.js installed
- MongoDB running locally (or MongoDB Atlas connection)

## Installation

1. Clone or download this project
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the root directory with:
   ```
   PORT=3000
   MONGO_URI=mongodb://localhost:27017/crud_app
   ```
4. Start the server:
   ```bash
   npm start
   ```

## API Endpoints

### Create a Book
- **POST** `/api/books`
- Body: `{ "title": "Book Title", "author": "Author Name", "publishedYear": 2023 }`

### Get All Books
- **GET** `/api/books`

### Get a Book by ID
- **GET** `/api/books/:id`

### Update a Book
- **PUT** `/api/books/:id`
- Body: `{ "title": "Updated Title", "author": "Updated Author", "publishedYear": 2024 }`

### Delete a Book
- **DELETE** `/api/books/:id`

## Example Usage

### Create a book:
```bash
curl -X POST http://localhost:3000/api/books \
  -H "Content-Type: application/json" \
  -d '{"title": "The Great Gatsby", "author": "F. Scott Fitzgerald", "publishedYear": 1925}'
```

### Get all books:
```bash
curl http://localhost:3000/api/books
```

### Update a book:
```bash
curl -X PUT http://localhost:3000/api/books/[BOOK_ID] \
  -H "Content-Type: application/json" \
  -d '{"title": "Updated Title"}'
```

### Delete a book:
```bash
curl -X DELETE http://localhost:3000/api/books/[BOOK_ID]
```

## Project Structure

```
crud-app/
  |-- models/
      |-- book.js          # Mongoose model
  |-- controllers/
      |-- bookController.js # CRUD operations
  |-- routes/
      |-- bookRoutes.js     # API routes
  |-- server.js            # Main server file
  |-- .env                 # Environment variables
  |-- package.json         # Dependencies
```

## Technologies Used

- Node.js
- Express.js
- MongoDB
- Mongoose
- dotenv 