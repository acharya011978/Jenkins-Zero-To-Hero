FROM maven:3.9.6-eclipse-temurin-17-alpine AS build
COPY . /build
WORKDIR /build
RUN mvn clean package -DskipTests

FROM eclipse-temurin:17-jdk-alpine
COPY --from=build /build/target/spring-boot-web.jar /opt/app/app.jar
ENTRYPOINT ["java","-jar","/opt/app/app.jar"]
