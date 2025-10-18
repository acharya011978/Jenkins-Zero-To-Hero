FROM maven:3.9.6-eclipse-temurin-17 AS build
COPY . /build
WORKDIR /build
RUN mvn clean package -DskipTests

FROM eclipse-temurin:17-jdk
COPY --from=build /build/target/*.jar /opt/app/app.jar
ENTRYPOINT ["java","-jar","/opt/app/app.jar"]
