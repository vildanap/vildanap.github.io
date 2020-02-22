## Travel review

**Project description:** The Travel Review website is for all users who want to get all the information about cities around the world in one easy way and in one place. The site allows users to share their experiences about visited cities with other users, which is made possible by leaving reviews. The review consists of entering comments/observations, photos and ratings by different criteria, such as gastronomic offer, cultural and artistic content, nightlife, transportation, etc. Based on user reviews, the site gives an insight into the best or worst rated cities. The site distinguishes three types of users: administrator, registered user and guest and access to the website resources depends on user type.

![Travel review](/images/front_travel_review.PNG)

### Microservices architecture

The application has been developed as a set of mini applications, which are developed as independent components and are communicating to each other using REST Web Services. The main purpose was to create a microservice based application in order to familiarize with microservice architectural style and note the advantages/disadvantages to monolithic architecture.

The first step was to identify individual components of Travel review application system, which will be developed independetly and have their set of responsibilities (modular approach). Identified were four components:

1. _Identity microservice: user management system and authentication_
2. _Location microservice: city management system (CRUD city)_
3. _Review microservice: review management system (CRUD review)_
4. _Image microservice: image management system (CRUD image)_

Microservices communicate with each other using **Eureka server (registry server)** and should be register inside Eureka server by unique name e.g. {nwt2_identity_ms}. After registered calling service fetches the registry from Eureka server and gets the instance of downstream service and gets data calling REST endpoint. 

A unified proxy interface that will delegate the calls to various microservices based on a URL pattern has been created (Zuul proxy). An API Gateway using **Spring Cloud Zuul Proxy** was also needed for security implenetation. Typically OAuth service for authentication and authorization is used for microservices, so user is only once authenticated and can later on make requests to other microservices separately. Using Zuul Filter AUTH HEADER will be forwarded to downstream services.

![Microservice architecture](/images/travel review.PNG)


### Security

Security was implemented on the application using the **Oauth2 specification**. Oauth2 involves creating an Authorization Server that will authenticate the user and assign a JWT token to him, later to access other Resource Servers. Authorization Server is implemented inside identity microservice since it covers user management system.

### Docker

Development and deployment effort for microservices architecture based applications is lately eased by **Docker technology**. Application is deployed using Docker tehnology. Each microservice contains a docker file containing the corresponding maven .jar executable file.
After a docker image is created for each service, the application is deployed via the docker compose which results in the lifting of all containers defined in its structure (docker-compose.yml).


For more implementation details see [GitHub project](https://github.com/vildanap/NWT_Tim2).
