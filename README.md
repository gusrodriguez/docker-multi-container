# Multi-container docker app.

## What's this?
It's an implementation of a multi-container application achitecture, by using docker-compose.

## What could it be useful for?
If you want a take a look at how to configure a docker-compose file with several docker containers.

The application implements the diagram below:

![alt text](https://github.com/gusrodriguez/docker-multi-container/blob/master/multi-container.png?raw=true)

- For the incoming request, nginx will decide based on the route, if it should serve the React app or the api content depending on the route.
- The React app will consume data from the Express Api.
- The Express Api will serve data to the React app and will consume data from a Postgres server and/or a Redis server.
- The Redis server will comunicate with a worker, that emulates a high workload of computing.

This is an intentional overkill architecture. The purpose of the project is not related to the optimization of the architecture neither the React application per se, but to be able to build a multi-container application and raise it up with docker-compose in a complex scenario.

### Usage
Navigate locally at:
```
http://localhost:3050/
```
