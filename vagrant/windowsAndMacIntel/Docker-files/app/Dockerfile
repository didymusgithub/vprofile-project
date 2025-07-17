# Stage 1: Build the app
FROM maven:3.9.9-eclipse-temurin-21-jammy AS build_image

WORKDIR /app

RUN git clone https://github.com/hkhcoder/vprofile-project.git

WORKDIR /app/vprofile-project

RUN git checkout docker && mvn clean install

# Stage 2: Deploy to Tomcat
FROM tomcat:10-jdk21

RUN rm -rf /usr/local/tomcat/webapps/*

# Ensure WAR name matches what's in the target directory
COPY --from=build_image /app/vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
