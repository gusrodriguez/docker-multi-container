Multi-container docker app.

The application implements the diagram below:

![alt text](https://github.com/gusrodriguez/docker-multi-container/blob/master/multi-container.png?raw=true)

- Once a request occurs, nginx will decide based on the route, if it should serve the React app or the api content depending on the route.
- The React app will consume data fro the Express Api.
- The Express Api will serve data to the React app and will consume data from a Postgres server and/or a Redis server.
- The Redis server will comunicate with a worker, that emulates a high workload of computing.

This is an intentional overkill architecture. The purpose of the project is not related to the   the optimization of the architecture neither the React application per se, but to be able to build a multi-container application and raise it up with docker-compose in a complex scenario.

Navigate locally at:
http://localhost:3050/