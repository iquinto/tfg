<!-- About this project -->
## About WORKINGSTUDENT

This is TFG project and it is made up of 4 elements (each one in its own GIT repository):

* A repository for <a href="https://github.com/iquinto/working-student-ui">frontend</a> code (working-student-ui)
* A repository for <a href="https://github.com/iquinto/working-student-app">backend</a> code (working-student-app)
* A repository for <a href="https://github.com/iquinto/working-student-cypress">E2E</a> testing
* A <a href="https://github.com/iquinto/tfg-uoc/blob/master/docker-compose.yml">docker-compose.yml</a> file to execute the project via docker images.

<p align="right">(<a href="#top">go up</a>)</p>

### Powered by
* [Spring Boot](https://spring.io/projects/spring-boot)
* [Vue](https://vuejs.org/)
* [PostgreSQL](https://www.postgresql.org/)
* [Docker](https://www.docker.com/)


## Configuration

#### Directory structure
Create a parent directory (tfg) where to save the downloaded or cloned repositories. The objective is to have the following directory structure for the  whole project:
```
tfg
├ README.md
├ docker-compose.yml
├ working-student-ui
├ working-student-app
└ working-student-cypress
```

#### Prepare project

<ol type="1">
  <li>Download or cloan <a href="https://github.com/iquinto/tfg"> current repository</a></li>
  <li>Download or cloan <a href="https://github.com/iquinto/working-student-ui" target="_blank"> working-student-ui repository</a></li>
  <li>Download or cloan <a href="https://github.com/iquinto/working-student-app" target="_blank"> working-student-app repository</a></li>
  <li>Download or cloan <a href="https://github.com/iquinto/working-student-cypres" target="_blank"> working-student-cypress repository</a></li>

  <li>Milk</li>
</ol>  




### Database

### Backend

### Frontend

### E2E Testing

### Docker Desktop / Docker Compose installation

Proceed to install Docker Compose following the steps described in the following guide: https://docs.docker.com/compose/install/ (according to your OS).

Once Docker Compose is installed, download the code in ZIP format or just clone the <a href="https://github.com/iquinto/tfg-uoc/blob/master/docker-compose.yml">.
```
epcsd-spring-main
├ README.md
├ docker-compose.yml
├ epcsd-spring-notification-main
└ epcsd-spring-showcatalog-main
```

<p align="right">(<a href="#top">go up</a>)</p>


### Basic infrastructure (dockers)

* Download the code in ZIP format or just clone the <a href="https://github.com/ppinedar/epcsd-spring">epcsd-spring</a> repository in the working folder (_epcsd-spring-main_ if the recommendation has been followed).

* From the work folder, run the command:

  ```sh
  docker compose up
  (Win)
  ```
  ```sh
  docker-compose up
  (Linux)
  ```
  
The following containers should start:

* epcsd-spring_adminer_1 - adminer, an SQL client
* epcsd-spring_kafka_1 - the kafka server
* epcsd-spring_db_1 - the postgresql database
* epcsd-spring_zookeeper_1 - kafka zookeeper

In order to verify that all containers are up and running, we will execute the following command:

  ```sh
  docker ps -a
  ```
  
  
We should see something like this:

![Screenshot_1](https://user-images.githubusercontent.com/72941559/155118965-78bfa6f1-24e0-461c-92c4-63df919d2ac1.png)

To check the operation, you can access the _Adminer_ panel at http://localhost:18080/ and make a query against the PostgreSQL DB that we have just instantiated with the following connection data:

* Engine: PostgreSQL
* Server: db
* User: epcsd
* Password: epcsd
* Schema: epcsd

<img width="513" alt="Screenshot_1" src="https://user-images.githubusercontent.com/72941559/156942365-9aa515cc-52fd-4c02-a21e-880911269985.png">

<img width="546" alt="Screenshot_2" src="https://user-images.githubusercontent.com/72941559/156942408-cbcb773d-b33d-406c-ba37-db980e3dbf64.png">


### ShowCatalog and Notification microservices

* Download the code in ZIP format or just clone the <a href="https://github.com/ppinedar/epcsd-spring-showcatalog">epcsd-spring-showcatalog</a> and <a href="https://github.com/ppinedar/epcsd-spring-notification">epcsd-spring-notification</a> repositories into the working folder (_epcsd-spring-main_ if the recommendation has been followed)
* Open the projects in the preferred development environment. __IMPORTANT:__ Each project has to be imported separately as they are separate deployment units.
* Verify proper build and run by starting the projects and checking that http://localhost:18081/swagger-ui/index.html and http://localhost:18082/swagger-ui/index.html are accessible

<p align="right">(<a href="#top">go up</a>)</p>


## Links to used tools, libraries and modules

* [Docker](https://www.docker.com/) / [Docker Compose](https://github.com/docker/compose)
* [Spring](https://spring.io/) / [Spring Boot](https://spring.io/projects/spring-boot)
  * [spring-data-jpa](https://spring.io/projects/spring-data-jpa)
  * [spring-data-jdbc](https://spring.io/projects/spring-data-jdbc)
  * [spring-kafka](https://spring.io/projects/spring-kafka)
* [Apache Kafka](https://kafka.apache.org/)
* [PostgreSQL](https://www.postgresql.org/)
* [Lombok](https://projectlombok.org/)
* [springdoc-openapi-ui (SwaggerUI for OpenApi 3)](https://github.com/springdoc/springdoc-openapi)


## Contact

Pau Pineda - ppineda0@uoc.edu

<p align="right">(<a href="#top">go up</a>)</p>



# WORKINGSTUDENT
### tfg-uoc docker compose
### Run project via docker compose
```
docker compose up --build
```

### Stop project
```
docker-compose down
```
### Clean Docker
#### 1. Stop All Docker Containers
```
docker kill $(docker ps -q)
```

#### 2. Delete all containers using the following command:
```
docker rm -f $(docker ps -a -q)
```

#### 3. Delete all containers including its volumes use,
```
docker rm -vf $(docker ps -aq)
```

#### 4. Delete all the images,
```
docker rmi -f $(docker images -aq)
```
#### 5. Delete all volumes using the following command:
```
docker volume rm $(docker volume ls -q)
```
