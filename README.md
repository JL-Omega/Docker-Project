# Pozos Application

![project](https://user-images.githubusercontent.com/18481009/84582395-ba230b00-adeb-11ea-9453-22ed1be7e268.jpg)


------------
## Introduction

This repository contains the source code and Docker configuration for the ***Pozos Application***. The Pozos Application is a simple application designed to list students, featuring a web server built with ***PHP*** and an API powered by ***Flask***. It is composed of multiple services that work together to provide various functionalities related to managing student information, hosting a website, and maintaining a Docker registry.

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

## Usage

Once the services are running, you can access the following components:

- **Website:** Access the website hosted on port 81. The result is shown in the screenshot below.
- 
  ![image](https://github.com/JL-Omega/Docker-project/assets/96908472/b5bb033d-1e9b-4671-b8d4-9018ee06c84b)

  Click on `List Student` and you will get the result below

  ![image](https://github.com/JL-Omega/Docker-project/assets/96908472/528f9bb7-cdb0-4290-ae1b-156e5453b83b)

  
- **Registry UI:** Access the Docker registry UI hosted on port 8081. The result is shown in the screenshot below.

  ![Screenshot_5](https://github.com/JL-Omega/Docker-project/assets/96908472/e5e6de96-f803-478d-becd-e0388711f252)

Don't forget to push images to the local registry by tagging the image with `localhost:5000` as shown in the screenshots below.

![Screenshot_3](https://github.com/JL-Omega/Docker-project/assets/96908472/fc134587-32a2-4b02-ab11-36796f94e4da)
![Screenshot_4](https://github.com/JL-Omega/Docker-project/assets/96908472/0a05d349-b15f-437b-bea1-09b6f88d0981)

## Application Structure

The application is composed of the following services:

- ***pozos-website:*** Frontend service for hosting a website.
- ***pozos-api:*** Backend service for managing student information.
- ***pozos-registry-ui:*** Frontend service for managing Docker images in the Docker registry.
- ***pozos-registry:*** Backend service for hosting a Docker registry.
  
## Configuration

### Docker Configuration

The Docker configuration for each service is specified in the ***docker-compose.yml*** files.

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
    
## Service Name and Port Synchronization

When modifying the name or port of the `pozos-api` service in the Docker Compose file (`docker-compose.yml`), it's essential to update the corresponding URL link in the `website/index.php` file.

The `website/index.php` file likely contains the URL endpoint used to connect the frontend with the backend API service. Any changes made to the service name or port should be reflected in this URL to ensure proper communication between the frontend and backend components.

Failure to synchronize these changes may result in connection errors or unexpected behavior when interacting with the Pozos Application. Always verify and update the URL link in the `website/index.php` file to maintain seamless communication between frontend and backend services.

## Configuration Synchronization

When configuring the `pozos-website` service in the Docker Compose file (`docker-compose.yml`), it's important to note that if you change the `USERNAME` or `PASSWORD` environment variables, you'll need to synchronize these changes with the `simple_api/student_age.py` file.

The `simple_api/student_age.py` file likely contains authentication logic that checks the provided username and password against the configured values. Therefore, any modifications to the credentials in the Docker Compose file should be mirrored in the Python script to ensure proper authentication between the frontend and backend components.

Failure to synchronize these changes may result in authentication errors or unexpected behavior when accessing the application. Always ensure consistency between the Docker Compose configuration and application logic to maintain the integrity and security of the Pozos Application.

## Contributing
If you'd like to contribute to this project, please fork the repository and submit a pull request.

## Maintainer
This project is maintained by Jean-Luc Mpande. You can reach out to the maintainer via email at mpandejl1@gmail.com or [LinkedIn](https://www.linkedin.com/in/jean-luc-mpande-75981a23b/).

## License
This project is licensed under the MIT License - see the [LICENSE] file for details.
 





