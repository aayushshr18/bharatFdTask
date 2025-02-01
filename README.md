# FAQ Management System

This is a simple FAQ management system built using **Express.js** and **MongoDB**, allowing users to register, log in, and access frequently asked questions (FAQs) with multilingual support.

## Features

- **User Management:**
  - Register a new user
  - Login to an existing user account
  
- **FAQ Management:**
  - CRUD operations for FAQs (Create, Read, Update, Delete)
  - Translations for FAQs to support multiple languages

## Installation

1. Clone the repository:
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2. Install the dependencies:
    ```bash
    npm install
    ```

3. Set up your `.env` file with MongoDB URI and any other necessary environment variables.

4. Start the application:
    ```bash
    npm start
    ```

The app will be running at `http://localhost:3000` by default.

## API Endpoints

### Authentication Routes (Auth)

#### **POST /register**

- **Description**: Registers a new user.
- **Request Body**:
  ```json
  {
    "username": "string",
    "email": "string",
    "password": "string"
  }
Response:
Success (201):
json
Copy
Edit
{
  "message": "User registered successfully"
}
Error (400): Invalid input or existing user.
POST /login
Description: Logs in an existing user.
Request Body:
json
Copy
Edit
{
  "email": "string",
  "password": "string"
}
Response:
Success (200):
json
Copy
Edit
{
  "message": "Login successful",
  "token": "jwt-token"
}
Error (401): Invalid email or password.
GET /faq
Description: Retrieves a list of FAQs.
Query Parameters:
lang (optional): The language code (default is en).
Response:
Success (200):
json
Copy
Edit
[
  {
    "question": "Question text",
    "answer": "Answer text"
  },
  {
    "question": "Another question",
    "answer": "Another answer"
  }
]
Error (500): Internal server error.
User Routes (v1)
GET /user
Description: Retrieves the details of the current logged-in user.
Response:
Success (200):
json
Copy
Edit
{
  "username": "string",
  "email": "string"
}
Error (401): Unauthorized (if not logged in).
PATCH /user
Description: Updates the logged-in user's details.
Request Body:
json
Copy
Edit
{
  "username": "string",
  "email": "string"
}
Response:
Success (200):
json
Copy
Edit
{
  "message": "User updated successfully",
  "user": {
    "username": "updated string",
    "email": "updated string"
  }
}
Error (400): Invalid input.
DELETE /user
Description: Deletes the current logged-in user.
Response:
Success (200):
json
Copy
Edit
{
  "message": "User deleted successfully"
}
Error (401): Unauthorized (if not logged in).
FAQ Routes (v1)
POST /faq
Description: Creates a new FAQ.
Request Body:
json
Copy
Edit
{
  "question": "string",
  "answer": "string"
}
Response:
Success (201):
json
Copy
Edit
{
  "question": "string",
  "answer": "string",
  "translations": {}
}
Error (500): Internal server error or invalid input.
GET /faq/:id
Description: Retrieves a single FAQ by ID.
Parameters:
id: The FAQ ID.
Query Parameters:
lang (optional): The language code (default is en).
Response:
Success (200):
json
Copy
Edit
{
  "question": "translated question text",
  "answer": "translated answer text"
}
Error (404): FAQ not found.
Error (500): Internal server error.
GET /faq
Description: Retrieves all FAQs.
Query Parameters:
lang (optional): The language code (default is en).
Response:
Success (200):
json
Copy
Edit
[
  {
    "question": "translated question text",
    "answer": "translated answer text"
  },
  {
    "question": "another translated question",
    "answer": "another translated answer"
  }
]
Error (500): Internal server error.
PUT /faq/:id
Description: Updates an existing FAQ by ID.
Parameters:
id: The FAQ ID.
Request Body:
json
Copy
Edit
{
  "question": "updated question",
  "answer": "updated answer"
}
Response:
Success (200):
json
Copy
Edit
{
  "question": "updated question",
  "answer": "updated answer",
  "translations": {}
}
Error (404): FAQ not found.
Error (500): Internal server error.
DELETE /faq/:id
Description: Deletes an FAQ by ID.
Parameters:
id: The FAQ ID.
Response:
Success (200):
json
Copy
Edit
{
  "message": "FAQ deleted successfully"
}
Error (404): FAQ not found.
Error (500): Internal server error.
Database
This application uses MongoDB for storing user information and FAQ data. The FAQ schema also includes a translations map that stores translations for different languages.

Dependencies
express: Web framework for Node.js
mongoose: MongoDB ODM
@vitalets/google-translate-api: Library for language translation
dotenv: Environment variable management
body-parser: Middleware to parse JSON requests
Running Tests
To run tests, ensure that you have set up test configurations and MongoDB in the environment. Then use a testing library like Jest or Mocha to run the tests.

Contributing
Feel free to fork this project and submit issues or pull requests. All contributions are welcome!

License
This project is licensed under the MIT License - see the LICENSE file for details.

sql
Copy
Edit

### What’s Included:
- Detailed API documentation with all routes and their respective request/response formats.
- Full descriptions of parameters, body data, and response examples for both success and error cases.
- Information about the database and dependencies.

This version should serve as a thorough reference for both developers and users interacting with your API. Let me know if there's anything more you'd like to add!






