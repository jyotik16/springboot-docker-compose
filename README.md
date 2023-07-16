
## How to Dockerize Spring Boot Application


### Spring Boot application will be packaged as jar file
* **
    ``` 
     <packaging>jar</packaging>
    <finalName>spring-boot-docker-app</finalName>
    ```
* In pom.xml file packaing must be present 
* finalName Of App will be same present inside the dockerFile.
* * **

### To run Spring Boot application we need to run jar file
```
mvn clean package
```

### Spring Boot provides embedded server for web applications

    GIT Hub repo : https://github.com/ashokitschool/spring-boot-docker-app.git

### Below is the Dockerfile for Spring Boot Application
```
FROM open-jdk:11

COPY target/app.jar /usr/app/

WORKDIR /usr/app/

EXPOSE 8080

ENTRYPOINT [ "java", "-jar", "app.jar" ]
```
### Create docker image of Spring boot app by using dockerfile

```
docker build -t sbootapp .
```
*  '.' denote the current directory 
*  Execute the above cmd in the directory where dockerfile is present.

### Run the docker image 
```agsl
docker run -d -p 9090:8080 sbootapp 
```
* -d detached mode
* -p define the port 
* spring boot app run at 8080 port
* we run the container at 9090 port
* sbootapp is docker image name

### Architecture
<img src='/images/img.png' height='100' width='100'>