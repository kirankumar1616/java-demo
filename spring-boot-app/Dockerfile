# Stage 1: Build the application with Maven
FROM maven:3.8.4-jdk-11 AS build
WORKDIR /app
COPY . /app
RUN mvn clean package
 
# Stage 2:
FROM openjdk:11-jre-slim
WORKDIR /app
COPY --from=build /app/target/*.jar /app/spring-boot-app.jar
 

ENTRYPOINT ["java", "-jar", "spring-boot-app.jar"]
