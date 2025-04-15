# ✅ Stage 1: Build with Java 21
FROM eclipse-temurin:21 AS build

WORKDIR /app
COPY . .

RUN ./gradlew clean build -x check -x test

# ✅ Stage 2: Run the app
FROM eclipse-temurin:21

WORKDIR /app
COPY --from=build /app/server-app/build/libs/server-app*.jar ./tolgee-server.jar

EXPOSE 8080
CMD ["java", "-jar", "tolgee-server.jar"]
