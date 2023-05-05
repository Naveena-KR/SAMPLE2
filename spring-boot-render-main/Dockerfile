#
# Build stage
#
FROM maven:3.6.0-jdk-11-slim AS build
COPY . .
RUN mvn clean package -DskipTests

#--from=build /target/demo-0.0.1-SNAPSHOT.jar demo.jar
# Package stage
#
FROM openjdk:11-jre-slim
COPY . .
ENV PORT=8080
EXPOSE 8080
ENTRYPOINT ["java","-jar","demo.jar"]
