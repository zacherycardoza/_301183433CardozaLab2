FROM maven:3.6.3-openjdk-11 AS build
WORKDIR /app
COPY . .
RUN mvn clean package

FROM openjdk:11-jre-slim
WORKDIR /app

COPY --from=build /app/target/*.war app.war
EXPOSE 8080
CMD ["java", "-jar", "app.war"]
