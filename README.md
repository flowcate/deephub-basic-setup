# DeepHub® Basic Setup

This project provides a completely configured “system” consisting of the DeepHub®, the DeepHub® UI and a containerized web server, acting as a reverse proxy, to simplify the overall usage and interaction of these components. For the orchestration between these three containers docker compose is used.

## Prerequisites
* [Docker](https://docs.docker.com/engine/install/)
* [Docker Compose](https://docs.docker.com/compose/install/)

## Running the application
* Open a shell.
* Invoke Docker Compose in the directory where your docker-compose.yml file resides.
```
docker-compose up -d
```
Now you have your own running DeepHub® instance that can be accessed with any modern web browser at the address: http://localhost:8081

To complement the DeepHub UI shown above, you may also make API calls to the [DeepHub REST API](https://docs.deephub.io/api_reference/restApi.html#/deep-hub-api-rest-api) while running the DeepHub locally. This can be done with a tool such as Postman or cURL. <br />
To interact with the REST API, you will need to use the following baseURL: http://localhost:8081/deephub/v1 <br />

Example:
```
curl http://localhost:8081/deephub/v1/zones/summary
```

For further information visit [docs.deephub.io](https://docs.deephub.io/installation_instructions/).
