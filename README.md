# Introduction

The DeepHub® is a lightweight, high-performance locating-middleware, that enables a seamless indoor and outdoor tracking of objects by integrating any locating technology (UWB, BLE, RFID, 5G, etc.) of any vendor through one single modern API.

The DeepHub is the premier implementation of an omlox hub, specified in the open locating standard omlox.

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

This command will automatically pull the necessary docker images from hub.docker.com and create docker containers before starting the latter. In case you want to see all log output immediately, invoke the former command omitting the "-d" parameter (deamon mode).

|:point_up: | It may become necessary to manually call ```docker-compose pull``` first. This is the case if a newer docker image with the same name got published and therefore needs to get "re-pulled". This should not happen in general as we release updates as docker images with a different/newer tag.|
|-----------|:---------------------------------------------------------------------------------------------------------------------------|

Now you have your own running DeepHub® instance that can be accessed with any modern web browser at the address: http://localhost:8081

To complement the DeepHub UI shown above, you may also make API calls to the [DeepHub REST API](https://docs.deephub.io/api_reference/restApi.html#/deep-hub-api-rest-api) while running the DeepHub locally. This can be done with a tool such as Postman or cURL. <br />
To interact with the REST API, you will need to use the following baseURL: http://localhost:8081/deephub/v1 <br />

Example:
```
curl http://localhost:8081/deephub/v1/zones/summary
```

For further information visit [docs.deephub.io](https://docs.deephub.io/installation_instructions/).
