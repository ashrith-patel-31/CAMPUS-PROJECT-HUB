FROM maven:3.9-eclipse-temurin-21 AS build
WORKDIR /app

COPY pom.xml .
COPY src ./src

RUN for i in 1 2 3 4 5; do mvn -B -Dmaven.wagon.http.retryHandler.count=5 -DskipTests clean package && exit 0; echo "Attempt $i failed; retrying in 20 seconds..."; sleep 20; done; exit 1

FROM eclipse-temurin:21-jre
WORKDIR /app

COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java","-jar","app.jar"]