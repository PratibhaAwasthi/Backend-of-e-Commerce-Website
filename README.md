# Back End of a e-commerce Website

A  backend API built in NodeJS for an online store. This application has APIs for Users, Products, and Orders.

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
