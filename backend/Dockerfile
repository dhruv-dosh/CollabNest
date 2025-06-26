# 1. Use official Maven image to build the application
FROM maven:3.9.4-eclipse-temurin-17 AS build

# 2. Set working directory
WORKDIR /app

# 3. Copy project files
COPY . .

# 4. Build the Spring Boot application (skip tests for faster build)
RUN mvn clean package -DskipTests

# 5. Use lightweight JDK image to run the built app
FROM eclipse-temurin:17-jdk-alpine

# 6. Set working directory
WORKDIR /app

# 7. Copy the packaged jar file from the build stage
COPY --from=build /app/target/*.jar app.jar

# 8. Expose the port your app runs on (as you mentioned: 5054)
EXPOSE 5054

# 9. Run the jar file
ENTRYPOINT ["java", "-jar", "app.jar"]
