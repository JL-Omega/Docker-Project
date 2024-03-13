# Pozos Application
This repo is a simple application to list student with a webserver (PHP) and API (Flask)

![project](https://user-images.githubusercontent.com/18481009/84582395-ba230b00-adeb-11ea-9453-22ed1be7e268.jpg)


------------
## Introduction

This repository contains the source code and Docker configuration for the Pozos Application. The Pozos Application is a system composed of multiple services that work together to provide various functionalities related to managing student information, hosting a website, and maintaining a Docker registry.

## Prerequisites

Before you begin, ensure you have the following installed:

- ***Docker***
- ***Docker Compose***

## Getting Started
To run the Pozos Application, follow these steps:
1. Clone this repository:
   ```bash
   git clone https://github.com/JL-Omega/Mini-Docker-project.git
   ```
2. Navigate to the cloned directory:
     ```bash
   cd Mini-Docker-project
   ```
3. Build and start the services using Docker Compose:
     ```bash
   docker-compose up -d
   ```

  The application services should now be up and running.

## Application Structure

The application is composed of the following services:

- ***pozos-website:*** Frontend service for hosting a website.
- ***pozos-api:*** Backend service for managing student information.
- ***pozos-registry-ui:*** Frontend service for managing Docker images in the Docker registry.
- ***pozos-registry:*** Backend service for hosting a Docker registry.
  
## Configuration

### Docker Configuration

The Docker configuration for each service is specified in the ***Dockerfile*** and ***docker-compose.yml*** files.

### Docker Image Deployment

The Dockerfile for the backend service ***pozos-website-backend*** was built and the resulting image was pushed to Docker Hub under the username ***jlmpande***. This Docker image contains the necessary dependencies and configurations to run the backend service.

The ***pozos-api*** service, which orchestrates the backend functionality, pulls the Docker image from the Docker Hub repository during container initialization. This ensures that the latest version of the backend service is always deployed when starting the application.

For more details on the Docker image and its configurations, please refer to the Dockerfile in the repository. If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

### Environment Variables

The environment variables can be configured for the following services:

- #### pozos-website:

  - ***USERNAME:*** Username for accessing the website.
  - ***PASSWORD:*** Password for accessing the website.

- #### pozos-registry-ui:

  - ***REGISTRY_URL:*** URL of the Docker registry.
  - ***REGISTRY_TITLE:*** Title of the Docker registry.
  - ***DELETE_IMAGES:*** Enable or disable image deletion.
  - ***CATALOG_ELEMENTS_LIMIT:*** Limit for the number of catalog elements.
 
## Usage

Once the services are running, you can access the following components:

  - ***Website:*** Access the website hosted on port 81.
  - ***Registry UI:*** Access the Docker registry UI hosted on port 8081.

## Contributing
If you'd like to contribute to this project, please fork the repository and submit a pull request.

## Maintainer
This project is maintained by Jean-Luc Mpande. You can reach out to the maintainer via email at mpandejl1@gmail.com or [LinkedIn](https://www.linkedin.com/in/jean-luc-mpande-75981a23b/).

## License
This project is licensed under the MIT License - see the LICENSE file for details.
 





