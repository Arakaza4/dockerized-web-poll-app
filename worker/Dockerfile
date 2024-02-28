FROM maven:3.8.4-jdk-11-slim as builder
WORKDIR /app

COPY . .
RUN mvn dependency:resolve \ 
package




FROM openjdk:11-jre-slim
WORKDIR /app
ENV PORT=5432
ENV HOST="127.0.0.1"
ENV USERNAME="postgres"
ENV PASSWORD="password"


COPY --from=build /app/target/worker-jar-with-dependencies.jar /app/worker.jar

CMD ["java","-jar","/app/worker.jar"]