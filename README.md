# Authentication API Documentation

A secure authentication API built with Express.js and PostgreSQL.

## Endpoints

### Register User

```http
POST /api/auth/register
```

**Request Body:**

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securepassword"
}
```

### Login User

```http
POST /api/auth/login
```

**Request Body:**

```json
{
  "email": "john@example.com",
  "password": "securepassword"
}
```

### Get User Profile

```http
GET /api/auth/me
```

**Headers:**

```
Authorization: Bearer YOUR_JWT_TOKEN
```

## Authentication

All protected endpoints require a JWT token in the Authorization header:

```
Authorization: Bearer YOUR_JWT_TOKEN
```

## Response Format

### Success Response

```json
{
  "success": true,
  "data": {
    "user": {
      "id": 1,
      "name": "John Doe",
      "email": "john@example.com",
      "created_at": "2024-03-10T12:00:00Z"
    }
  }
}
```

### Error Response

```json
{
  "success": false,
  "error": "Error message"
}
```

## Setup

1. Install dependencies: `npm install`
2. Set environment variables in `.env`
3. Start server: `npm run dev`
