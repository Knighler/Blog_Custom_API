# Express Blog API

This is a simple RESTful API built with Express.js for managing blog posts. It supports CRUD (Create, Read, Update, Delete) operations on blog posts stored in an in-memory data store.

## Features

- Retrieve all posts
- Retrieve a specific post by ID
- Create a new post
- Update specific fields of a post
- Delete a post

## Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v14 or higher)
- npm (comes with Node.js)

## Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory:

   ```bash
   cd express-blog-api
   ```

3. Install the dependencies:

   ```bash
   npm install
   ```

## Running the Application

1. Start the server:

   ```bash
   node app.js
   ```

2. The API will run at:

   ```
   http://localhost:4000
   ```

## API Endpoints

### 1. Get All Posts

**Endpoint:** `GET /posts`

Retrieves all blog posts.

**Response:**

```json
[
  {
    "id": 1,
    "title": "The Rise of Decentralized Finance",
    "content": "Decentralized Finance (DeFi)...",
    "author": "Alex Thompson",
    "date": "2023-08-01T10:00:00Z"
  },
  ...
]
```

### 2. Get a Specific Post by ID

**Endpoint:** `GET /posts/:id`

Retrieves a single post by its ID.

**Parameters:**

- `id` (integer): ID of the post.

**Response:**

```json
{
  "id": 1,
  "title": "The Rise of Decentralized Finance",
  "content": "Decentralized Finance (DeFi)...",
  "author": "Alex Thompson",
  "date": "2023-08-01T10:00:00Z"
}
```

### 3. Create a New Post

**Endpoint:** `POST /posts`

Creates a new blog post.

**Request Body:**

```json
{
  "title": "New Post Title",
  "content": "Content of the new post.",
  "author": "Author Name"
}
```

**Response:**

```json
[
  {
    "id": 1,
    "title": "The Rise of Decentralized Finance",
    "content": "Decentralized Finance (DeFi)...",
    "author": "Alex Thompson",
    "date": "2023-08-01T10:00:00Z"
  },
  {
    "id": 4,
    "title": "New Post Title",
    "content": "Content of the new post.",
    "author": "Author Name",
    "date": "2023-08-15T14:00:00Z"
  }
]
```

### 4. Update a Post (Partial Update)

**Endpoint:** `PATCH /posts/:id`

Updates one or more fields of an existing post.

**Parameters:**

- `id` (integer): ID of the post.

**Request Body (optional fields):**

```json
{
  "title": "Updated Title",
  "content": "Updated content."
}
```

**Response:**

```json
{
  "id": 1,
  "title": "Updated Title",
  "content": "Updated content.",
  "author": "Alex Thompson",
  "date": "2023-08-15T14:00:00Z"
}
```

### 5. Delete a Post

**Endpoint:** `DELETE /posts/:id`

Deletes a post by its ID.

**Parameters:**

- `id` (integer): ID of the post.

**Response:**

```json
[
  {
    "id": 1,
    "title": "The Rise of Decentralized Finance",
    "content": "Decentralized Finance (DeFi)...",
    "author": "Alex Thompson",
    "date": "2023-08-01T10:00:00Z"
  }
]
```

## Example Usage

You can test the API using tools like [Postman](https://www.postman.com/) or [curl](https://curl.se/).

### Example curl Commands

- Get all posts:

  ```bash
  curl -X GET http://localhost:4000/posts
  ```

- Get a specific post:

  ```bash
  curl -X GET http://localhost:4000/posts/1
  ```

- Create a new post:

  ```bash
  curl -X POST -H "Content-Type: application/json" -d '{"title": "New Post", "content": "Content of the new post.", "author": "Author"}' http://localhost:4000/posts
  ```

- Update a post:

  ```bash
  curl -X PATCH -H "Content-Type: application/json" -d '{"title": "Updated Title"}' http://localhost:4000/posts/1
  ```

- Delete a post:

  ```bash
  curl -X DELETE http://localhost:4000/posts/1
  ```

## Notes

- The data is stored in memory, so it will reset every time the server restarts.
- This project is intended for learning purposes and does not include a database integration.

## License

This project is open-source and available unde
