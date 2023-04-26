# Introduction

The DeepHub® is a lightweight, high-performance locating-middleware, that enables seamless indoor and outdoor tracking of objects by integrating any locating technology (UWB, BLE, RFID, 5G, etc.) of any vendor through one single modern API.

The DeepHub is the premier implementation of an omlox hub, specified in omlox - the open locating standard.

# DeepHub® Basic Setup

This project provides a completely configured “system” consisting of the DeepHub®, the DeepHub® UI and a containerized web server, acting as a reverse proxy, to simplify the overall usage and interaction of these components. For the orchestration between these three containers, Docker Compose is used.

## Prerequisites
* [Docker](https://docs.docker.com/engine/install/)
* [Docker Compose](https://docs.docker.com/compose/install/)

|:point_up: | We only support the operation of a DeepHub docker image in the native version for a CPU. On Windows and Linux this is typically the Intel x86_64 version, same for Intel-based macOS devices. In case you have a new ARM-based macOS device, the native ARM docker image should be pulled automatically. 
|-----------|:---------------------------------------------------------------------------------------------------------------------------|

## Running the application
* Open a shell.
* Invoke Docker Compose in the directory where your docker-compose.yml file resides.
```
docker compose up -d
```

This command will automatically pull the necessary docker images from hub.docker.com, create docker containers, and start the containers. In case you want to see all log output immediately, invoke the former command omitting the "-d" parameter (deamon mode).

|:point_up: | It may be necessary to manually call ```docker compose pull``` first. This is the case if a newer docker image with the same name was published and therefore needs to get "re-pulled". This should not happen in general as we release updates as docker images with a different/newer tag.|
|-----------|:---------------------------------------------------------------------------------------------------------------------------|

Now you have your own running DeepHub® instance that can be accessed with any modern web browser at the address: http://localhost:8081

Calling this URL will redirect you to http://localhost:8081/deephub-admin-ui/ which is the so-called "Admin UI" of the DeepHub; i.e. the setup and configuration tool. There is also the so-called "Kiosk UI" that focus on everyday usage with a large LiveView and advanced search capabilities. The latter can be reached at http://localhost:8081/deephub-kiosk-ui/.


To complement the DeepHub UI shown above, you may also make API calls to the [DeepHub REST API](https://docs.deephub.io/api_reference/restApi.html#/deep-hub-api-rest-api) while running the DeepHub locally. This can be done with a tool such as Postman or cURL. <br />
To interact with the REST API, you will need to use the following baseURL: http://localhost:8081/deephub/v1 <br />

Example:
```
curl http://localhost:8081/deephub/v1/zones/summary
```

For more information, visit [docs.deephub.io](https://docs.deephub.io/installation_instructions/).
