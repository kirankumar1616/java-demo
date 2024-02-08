FROM maven:3.8.4-jdk-11
WORKDIR /app
COPY . /app
RUN mvn instal
RUN mvn clean package 
COPY /target/*.jar /app/spring-boot-app.jar
ENTRYPOINT ["java","-jar","spring-boot-app"]
