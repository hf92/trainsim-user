# Train Sim User

A work-in-progress application to simulate purchasing train tickets. This project is a sub-project of the micro-service version of Train Sim, modified from the monolithic version and is used for an assignment of SE 577 at Drexel University.

Please do not hesitate to contact the TAs (especially Jason Lefever or Hongzhou Fang) with any questions.

## Getting Started
The following tools are required to build and run this project: Docker, Docker Compose, Maven, Java 8, and npm.

The project contains 3 sub-projects, Trainsim-itinerary, Trainsim-user and Trainsim-client. Each directory of the project contains a docker-compose file. From the root of each directory run:

```
mvn clean install
docker-compose up
```

You should then be able to visit https://localhost:8000/ in your browser. Ignore the certificate error and you will be greeted with the homepage. (The certificate error happens because it is self-signed. It is not a concern because we are running locally.)

## Structure

### Trainsim-itinerary
Contains three services. 
- Trainsim-itinerary-service is spilt from Trainsim-api, provides stops and itinerary query under /api/itinerary at localhost:8001
- Trainsim-itinerary-db is the database linked to Trainsim-itinerary-service.
- Trainsim-planner is unchanged.

### Trainsim-user (This Repo)
Contains two services. 
- Trainsim-user-service is spilt from Trainsim-api, provides user login under /api/user at localhost:8002
- Trainsim-user-db is the database linked to Trainsim-user-service.

### Trainsim-client
The same Trainsim-client, the nginx config is changed to redirect requests to localhost:8001 and localhost:8002 instead of trainsim-api.

## Development and Debugging
Just follow the guide in the monolithic repo.


