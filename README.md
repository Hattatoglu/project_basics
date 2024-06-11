# Project Basics

This repository contains the basics of a microservice architecture project. The project is structured hierarchically with `server-parent` and `service-parent` modules to manage server and service components, respectively.

## Project Structure

### 1. Project Basic

The main project that includes the following components:

- **server-parent:** Parent project for all server projects.
  - **server-gateway:** Gateway service using Spring Gateway.
  - **server-discovery:** Discovery service using Spring Eureka Server.
  - **server-config:** Configuration service using Spring Config Server.
  - **server-zipkin:** Distributed tracing service using Zipkin Server.
- **service-parent:** Parent project for all service projects.
  - Currently, no services are added, but the infrastructure is ready for future services.

## Technologies and Tools Used

- **Spring Boot**: For creating and managing microservices.
- **Spring Cloud Gateway**: For the gateway service.
- **Spring Cloud Eureka Server**: For service discovery and registry.
- **Spring Cloud Config Server**: For centralized configuration management.
- **Zipkin**: For distributed tracing of microservices.
- **Docker**: For containerizing and managing applications.
- **Docker Compose**: For managing multi-container applications easily.

## Setup and Running

### 1. Maven Build

You can build the project from the root directory using the following command:

bash:
mvn clean install

### 2. Docker Build

To create Docker images for each service, navigate to the respective directories and run:

bash:
docker build -t <image-name> .

### 3. Docker Compose

You can run the project using the docker-compose files located under the docs directory. Separate docker-compose files are available for each service.

For example, to run the server-gateway service:

bash:
cd docs
docker-compose -f docker-compose-gateway.yml up

### 4. Service Configuration

Configuration for each service is located in the respective application.yml or application.properties files.

    Server Config configurations: server-config/src/main/resources/application.properties
	Server Gateway configurations in Server Config: server-config/src/main/resources/microservices/server-gateway.properties
    Server Discovery configurations in Server Config: server-config/src/main/resources/microservices/server-eureka.properties
	
	Server Gateway Server Config configuration: server-gateway/src/main/resources/application.properties
	Server Discovery Server Config configuration: server-discovery/src/main/resources/application.properties

## Development

To develop and add new services, use the server-parent and service-parent projects. Follow these steps to add a new service:

    Create a new Spring Boot project under server-parent or service-parent.
    Add the necessary configurations and dependencies.
    Build the project using mvn clean install and create Docker images.

## Contributing

If you want to contribute, please send a pull request or open an issue. We welcome all feedback.

## License

This project is licensed under the MIT License. For more details, refer to the LICENSE file.

##
This project provides a basic structure for a microservice architecture and serves as a starting point for those looking to develop and customize their projects.
