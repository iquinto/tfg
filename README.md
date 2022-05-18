<!-- About this project -->
## About WORKINGSTUDENT

This is TFG project and it is made up of 4 elements (each one in its own GIT repository):

* A repository for <a href="https://github.com/iquinto/working-student-ui">frontend</a> code (working-student-ui)
* A repository for <a href="https://github.com/iquinto/working-student-app">backend</a> code (working-student-app)
* A repository for <a href="https://github.com/iquinto/working-student-cypress">E2E</a> testing
* A <a href="https://github.com/iquinto/tfg/blob/master/docker-compose.yml">docker-compose.yml</a> file to execute the project via docker images.

<p align="right">(<a href="#top">go up</a>)</p>

## Configuration

### Directory structure
Create a parent directory (tfg) where to save the downloaded or cloned repositories. The objective is to have the following directory structure for the  whole project:
```
tfg
├ README.md
├ docker-compose.yml
├ working-student-ui
├ working-student-app
└ working-student-cypress
```

### Prepare project
<ol type="1">
   <li>
    Download
    <a href="https://github.com/iquinto/tfg/blob/master/docker-compose.yml"> 
      docker-compose.yml</a> file or clone <a href="https://github.com/iquinto/tfg"> current </a> 
     repository to execute the whole project via docker compose (docker image). Check <a href="#docker"> here </a>  for instructions 
  </li>
  <li>
    Download (zip) or cloan 
    <a href="https://github.com/iquinto/working-student-ui" target="_blank"> working-student-ui  </a> 
    repository to install Vue project for frontend (<i>follow instruction in the repositoy for installation</i>).
  </li>
  <li>
    Download (zip) or cloan 
    <a href="https://github.com/iquinto/working-student-app" target="_blank"> working-student-app </a> 
    repository to install Springboot project for backend (<i>follow instruction in the repositoy for installation</i>).
  </li>
  <li>
    Download (zip) or cloan 
    <a href="https://github.com/iquinto/working-student-cypres" target="_blank"> working-student-cypress </a>
     repository to install Cypress E2E testing (<i>follow instruction in the repositoy for installation</i>).
  </li>



</ol>  


### Powered by
* [Spring Boot](https://spring.io/projects/spring-boot)
* [Vue](https://vuejs.org/)
* [PostgreSQL](https://www.postgresql.org/)
* [Docker](https://www.docker.com/)


<span id="docker"></span>
## Docker Desktop / Docker Compose installation

Proceed to install Docker Compose following the steps described in the following guide: https://docs.docker.com/compose/install/ (according to your OS).

Once Docker Compose is installed you can execute the following commands:

* From the work folder, run the command:
  ```sh
  docker compose up
  (Win)
  ```
  ```sh
  docker-compose up
  (Linux)
  ```   
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
