# Docker
How to use Docker step by step

Steps for Docker-
1.	Maven build- install clean to create jar
2.	Add Dockerfile in project-
FROM openjdk:8
ADD target/<NameOfJar>.jar <GiveName>.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/<GiveName>.jar"]

Eg:
FROM openjdk:8

ADD target/demo-0.0.1-SNAPSHOT.jar demo.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/demo.jar"]

3.	Open powershell at projects directory
4.	Run this commands in powershell-
•	Docker build -t <GivenName> .    eg: Docker build -t demo . 
•	docker run -d -p 8080:8080 <GivenName>  eg: docker run -d -p 8080:8080 demo
•	docker images (to see all the images)
To Push Image on repository in docker hub
•	docker tag <givenName> <dockerId>/<repositoryName>:<tagNameOfImage>  eg: docker tag demo imnachiket/demo:latest
•	docker push <dockerId>/<reposirotyName>:<tagNameOfImage>   (make sure to sign in on docker desktop)  eg: docker push imnachiket/demo:latest
•	docker pull <repositoryName> eg: docker pull imnachiket/demo

