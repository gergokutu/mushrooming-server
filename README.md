# Mushrooming - Server
Server side of the mushrooming board game when you can play in different forests after creating a user and logging in.

## Project Structure
The project was developed by using Node.js.

## Deployment 
This project is currently deployed with Heroku and available with the latest master version here: [mushrooming-server](https://mushrooming-server.herokuapp.com)

    
## Technologies used
- Express: to expose the REST services
- Cors: to allow different host to consume the exposed service
- JWT: to handle the login/authentication, separate middleware function handles the authentication
- PostgreSQL: to store necessary data about users and the game
- Docker: to create a separate container for the database
- Bcrypt: to encrypt user passwords stored in the database

## Setup
Please note that in order to run the server locally you must also start a Postgres container
using the following commands:

```bash
$ docker run -p 5432:5432 --name mushrooming -e POSTGRES_PASSWORD=secret -d postgres
```
- git clone
- npm install
- npm run dev

It will start the node server on the port `5000`

### Endpoints




### How to start this project locally
```sh 
npm run start
```
It will start the node server on the port `5000`

