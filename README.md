# e-learning-demo
this is a demo web application using angular 7 and spring boot (version : 2.1.0.RELEASE)

## Installation Guides

### Required Tools

- Node v8+ for npm
- Anguar 7
- Java 8+
- maven v3+
- postman v2+ (To test rest-webservice)


### Run

#### Angular frontend web application

- Go to frontend directory and run the following commands
- $ npm install 		(to install all angular modules)
- $ ng serve -o			(to start the application)

#### Spring boot Rest-webservice
- Go to rest-webservice directory and run the following command
- $ mvn spring-boot:run 		(to build and start the service)


### Test

#### Angular frontend web application
- Go to http://localhost:4200/, you will be redirect tom login page.
- click on register to create new student account.
- after registration you will be redirected to home page
- click on menu-item (course) and start manage course registrations

#### Spring boot Rest-webservice
- you can test the rest-webservice by using swagger-ui web-application or  postman tool

##### Using Swagger-ui
- Go to http://localhost:8080/e-learning/swagger-ui.html#/
- you will be asked for username and password
	- username: admin
	- password: admin
- under student controller, you can find all exposed CRUD operations. and you can test it with the provided json samples.

##### Postman
- export postman collection (rest-webservice/testing/e-learning-webservice.postman_collection.json) into postman.
- test all requests

## Example Requests

- All request must be include basic authentication with pre-created student account
  - username : ${student-username}
  - password : ${student-password}
- by default, there is already created student account with the following credential
  - username : admin
  - password : admin
### GET http://localhost:8080/e-learning/api/students
- retreive all students accounts
```json
[
  {
    "birthdate": "2019-05-26T00:13:15.845Z",
    "email": "string",
    "gender": "string",
    "id": 0,
    "name": "string",
    "password": "string",
    "username": "string"
  }
]

```

### POST http://localhost:8080/e-learning/api/students
- create new student account
```json
{
  "birthdate": "2019-05-26T00:12:03.113Z",
  "email": "string",
  "gender": "string",
  "id": 0,
  "name": "string",
  "password": "string",
  "username": "string"
}
```

### GET http://localhost:8080/e-learning/api/students/${student-id}
- retreive student by id
```json

```
### PUT http://localhost:8080/e-learning/api/students/${student-id}
- update student
```json
{
  "birthdate": "2019-05-26T00:15:36.669Z",
  "email": "string",
  "gender": "string",
  "id": ${student-id},
  "name": "string",
  "password": "string",
  "username": "string"
}
```
### DELETE http://localhost:8080/e-learning/api/students/${student-id}
- delete student by id

### GET http://localhost:8080/e-learning/api/students/${student-id}/courses
- retreive student courses
```json
[
  {
    "description": "string",
    "instructor": "string",
    "lastUpdated": "2019-05-26T00:16:56.193Z",
    "name": "string",
    "publishDate": "2019-05-26T00:16:56.193Z",
    "totalHours": 0
  }
]
```
### POST http://localhost:8080/e-learning/api/students/${student-id}/courses
- register in course
```json
{
  "description": "string",
  "instructor": "string",
  "lastUpdated": "2019-05-25T23:58:17.380Z",
  "name": "string",
  "publishDate": "2019-05-25T23:58:17.380Z",
  "totalHours": 0
}
```
### GET http://localhost:8080/e-learning/api/students/${student-id}/courses/${course-id}
- retreive student course
```json
{
  "description": "string",
  "id": 0,
  "instructor": "string",
  "lastUpdated": "2019-05-26T00:18:39.910Z",
  "name": "string",
  "publishDate": "2019-05-26T00:18:39.910Z",
  "totalHours": 0
}
```
### DELETE http://localhost:8080/e-learning/api/students/${student-id}/courses/${course-id}
- unregister from course
 

