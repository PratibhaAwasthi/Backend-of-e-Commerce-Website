# Backend API for an Online Store

## Project Summary:
This project involves building a RESTful API in Node.js that will serve as the backend for an online store. The API will allow users to browse an index of all products, view details of a single product, and add products to an order which can be viewed on a cart page. The API will also handle user authentication and authorization using JWTs. The API will be built using Node.js and Express, with a Postgres database for data storage. The API will also use npm packages such as dotenv, db-migrate, jsonwebtoken, and jasmine for managing environment variables, database migrations, working with JWTs, and testing, respectively.

## Project Goals:

* Develop a RESTful API in Node.js that meets the requirements of the online storefront.
* Implement the required API endpoints for products, users, and orders.
* Handle user authentication and authorization using JWTs.
* Use a Postgres database for data storage.
* Ensure the API is scalable and performant.
* Ensure the API is secure and follows best practices for web development.
* Use npm packages such as dotenv, db-migrate, jsonwebtoken, and jasmine for managing environment variables, database migrations, working with JWTs, and testing, respectively. 

## Project Timeline:

* Research and planning: 1 week
* API development: 8 weeks
* Testing and debugging: 2 weeks
* Deployment and launch: 1 week

## API Endpoints:
The API will have the following endpoints:

### Products

* Index (GET /api/products )
* Show (GET /api/products/:id)
* Create [token required] (POST /api/products/create)
* Update [token required] (PUT /api/products/:id)
* Delete [token required] (DELETE /api/products/:id)

### Users

* Index [token required] (GET /api/users)
* Show [token required] (GET /api/users/:id)
* Create (POST /api/users)
* Update [token required] (PUT /api/users/:id)
* Delete [token required] (DELETE /api/users/:id)

### Orders

* Index [token required] (GET /api/orders)
* Show [token required] (GET /api/orders/:id)
* Create (POST /api/orders)
* Update [token required] (PUT /api/orders/:id)
* Delete [token required] (DELETE /api/orders/:id)
* Current Order by user (GET /api/orders/current-orders) [token required] (args: user id)

Overall, this project aims to build a reliable, scalable, and secure RESTful API that meets the requirements of an online storefront. By using Node.js and Postgres, we can ensure that the API is performant and scalable, while using JWTs for user authentication and authorization ensures that the API is secure. With thorough testing and debugging, we can ensure that the API meets all requirements and is ready for deployment and launch.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine.

### Prerequisites

To execute this project, you'll need to install the following modules and dependencies:

```
docker-compose   # To run the Postgres database on Docker
node 12          # To run the application
yarn             # For dependency management
```

### Installation Instruction

To install the project dependencies, just execute the following command:

```bash
yarn
```

### Setup environment
To begin, make a `.env` file with all of the necessary environment variables:

```bash
POSTGRES_PASSWORD="password"
POSTGRES_USER="postgres"
POSTGRES_DB="store"
DATABASE_URL="postgresql://postgres:password@localhost:5432/store"
ROOT_USER_PASSWORD="password"
SALT_ROUNDS="10"
JWT_SECRET="super-secure-jwt-secret"
```

Then, on Docker, start the Postgres server:

```bash
docker-compose up
```

Check to see whether Postgres has a database named `store`, and if not, create one

After that, you must do the database migrations:
```bash
yarn migrations up
```

## Activating the program

To start the application in watch mode, use the following command:
```bash
yarn run watch
```

To start the program in node, use the following command:
```bash
yarn start
```
***Note:** The application will generate the following root user on the first run, which you may utilize to create other users:*
```json
{
  "id": "root",
  "password": "{process.env.ROOT_USER_PASSWORD}",
  "firstname": "Root",
  "lastname": "Root",
  "superuser": true
}
```

## Running the unit tests

To run the unit tests, type the following command:
```bash
yarn test
```

## Built With

* NodeJS
* Yarn
* db-migrate
* Express
* TypeScript
* Jasmine
