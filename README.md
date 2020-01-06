# Mushrooming - Server
Server side of the mushrooming on-line board game where you can play in different forests (separate lobbies) after creating a user and logging in.

## Project Structure
The project was developed by using Node.js.

## Deployment 
This project is currently deployed with Heroku and available with the latest master version here: [mushrooming-server](https://mushrooming-server.herokuapp.com)

    
## Technologies used
- Express.js: to expose the REST services
- JSON SSE: to stream information to different channels (necessary because of the lobby-style game)
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
You also need to run the following commands:

```bash
$ git clone
```
```bash
$ npm install
```
```bash
$ npm run dev
```

It will start the node server on the port `4000`

### Endpoints
You can find all the endpoints in the `./router.js` file. Endpoints is created by following the RESTful principles.

- router.get('/stream') >> update the game in different forests
- router.post('/forest') >> create forest
- router.post('/join/:id') >> user can join to a forest (enter to separate lobby)
- router.put( '/start/:id1) >> start a game
- router.put('/roll/:id') >> roll a dice (play the game), random roll from 1 to 6, also updates mushroomer location in the forest (player position on the board) and the mushroomer's points due to landing on empty, good or bad mushroom field
- router.post('/user') >> create a user, password encrypted with bcrypt
- router.post('/login') >> handles user login/authentication, JWT + bcrypt
- router.get('/secret-endpoint') >> only for testing reason, authentication check

