FROM gradle:jdk17-focal AS build
WORKDIR "/home/app"
MAINTAINER Emin Israfilzade
ADD . .
#COPY gradle/ gradle
#COPY gradlew build.gradle ./
#RUN gradle clean build


FROM openjdk:17-alpine
WORKDIR "/home/app"
ARG JAR_FILE=/home/app/build/libs/ms-booking-1.0.0.jar
EXPOSE 8080
COPY --from=build ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","app.jar"]