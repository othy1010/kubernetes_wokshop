FROM maven AS build
WORKDIR /wordsmith/api
COPY pom.xml .
COPY src ./src
RUN mvn clean package
# run
FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY --from=build /wordsmith/api/target .

EXPOSE 8080  
ENTRYPOINT [ "java","-jar","/app/words.jar" ]
