# Use an official Maven image to build the application
FROM maven:3.9.4-eclipse-temurin-17 AS build

# Set the working directory inside the container
WORKDIR /app

# Copy the project files into the container
COPY . .

# Build the application using Maven
RUN mvn clean package -DskipTests

# Use a minimal JDK runtime image to run the app
FROM eclipse-temurin:17-jdk-alpine

# Set working directory
WORKDIR /app

# Copy the jar from the build stage
COPY --from=build /app/target/*.jar app.jar

# Expose the backend port
EXPOSE 5054

# Run the jar file
ENTRYPOINT ["java", "-jar", "app.jar"]
