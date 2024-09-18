Railway Management API
Project Overview

This project is a Railway Management System API that allows users to:

    Check train availability between stations.
    View seat availability for a specific train.
    Book seats after logging in.
    Admins can add or update trains.

The system is optimized to handle race conditions when multiple users try to book seats at the same time.
Author

    Name: Ayush Giri
    Email: agiri_be20@thapar.edu

Tech Stack

    Backend: Node.js with Express.js
    Database: MySQL
    Authentication: JWT (JSON Web Tokens)
    Environment Variables: dotenv

Setup Instructions
Prerequisites

    Node.js
    MySQL

Steps to Run the Project

    Clone the repository.

    bash

git clone <your-repo-url>
cd railway-management

Install dependencies.

bash

npm install

Create an .env file in the root directory of the project and add the following details:

bash

DB_HOST=localhost
DB_USER=root
DB_PASS=your_mysql_password
DB_NAME=railway_management
JWT_SECRET=your_jwt_secret
API_KEY=your_api_key

Set up the database. You can run the provided SQL script to create the required tables.

bash

mysql -u root -p < init.sql

Start the server.

bash

    node app.js

    The server will run on http://localhost:3000/.

API Endpoints
User Routes

    POST /api/users/register - Register a new user.
    POST /api/users/login - Log in a user and receive an authentication token.

Admin Routes (Requires API Key)

    POST /api/trains/add - Add a new train (only admin can do this).

User Routes (Requires JWT Token)

    GET /api/trains/availability - Check train availability between stations.
    POST /api/trains/book - Book a seat on a train.
    GET /api/bookings/details - Get specific booking details.

Security

    Admin endpoints are protected with an API key.
    User actions like booking seats and viewing bookings require JWT authentication.

Database

You can find the database schema in the init.sql file, which creates the necessary tables for users, trains, and bookings.
Future Improvements

    Implement more comprehensive error handling.
    Add pagination for large datasets.
    Optimize race condition handling further by using database transactions.

This should be all you need for the README.md file. Just replace <your-repo-url> with the actual GitHub repository URL after you've created it.
