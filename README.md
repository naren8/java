# Simple Spring boot project with CRUD REST endpoint using MySQL database
### 
## Before running project
Complete below action before starting spring boot server
1. Make sure mysql server is runngin on the local system.
2. Run `create database da;` folllowed by `use database da;`
3. Then run on local mysql server ```CREATE TABLE `task` (
  `completed` bit(1) DEFAULT NULL,
  `id` bigint NOT NULL AUTO_INCREMENT,
  `description` varchar(255) DEFAULT NULL,
  `title` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;```
4. You can update the config, if you want to, such as server port,mysql user credentials in file `java-repo/demo/src/main/resources/application.properties`. This project works with default config in this file given you follow all the steps.

## Authenticaiton
Server uses basic authentication with username: `admin` and password `admin` for all the endpoints

## Postman collection
https://grey-comet-7429.postman.co/workspace/public~9f5c5886-619d-41e3-bf40-10da76011489/collection/8374357-9a19524a-a336-49c0-bcf4-8f9db471c9c8?action=share&creator=8374357

## Running the project
1. Go to dir `java-repo/demo/`
2. Build project by running `./gradlew clean build`
3. Run server `./gradlew bootRun`

## Endpoints
### Create task
```
curl --location 'http://localhost:8080/v1/tasks' \
--header 'Content-Type: application/json' \
--header 'Authorization: Basic YWRtaW46YWRtaW4=' \
--data '{
    "title": "first task",
    "description":"first task description",
    "completed": false
}'
```
### Get task list
```
curl --location 'http://localhost:8080/v1/tasks' \
--header 'Authorization: Basic YWRtaW46YWRtaW4='
```

   
