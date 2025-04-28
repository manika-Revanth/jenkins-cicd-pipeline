# Use OpenJDK 17 as the base image (for Java 17 support)
FROM openjdk:17-jdk-slim

# Simply the artifact path
ARG artifact=target/spring-boot-web.jar

# Set the working directory inside the container
WORKDIR /opt/app

# Copy the built JAR file from target (make sure to build it first using `mvn clean package`)
COPY target/spring-boot-web.jar app.jar

# Run the Spring Boot application when the container starts
ENTRYPOINT ["java", "-jar", "app.jar"]

