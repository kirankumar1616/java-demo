FROM maven:3.8.4-jdk-11 AS builder

WORKDIR /app
COPY . /app
RUN mvn clean package

FROM openjdk:11-jre-slim

WORKDIR /app
COPY --from=builder /app/target/*.jar app/spring-boot-app.jar

ENTRYPOINT ["java", "-jar", "app/spring-boot-app.jar"]
