FROM maven:3.9.11-eclipse-temurin-17 AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests


FROM eclipse-temurin:17-jre-noble
WORKDIR /app
COPY --from=build /app/target/gateway-0.0.1-SNAPSHOT.jar .
CMD [ "java", "-jar", "gateway-0.0.1-SNAPSHOT.jar" ]
