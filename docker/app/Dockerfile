# ✅ Use Java 21
FROM eclipse-temurin:21

WORKDIR /app

# ✅ Download the prebuilt latest Tolgee server JAR
ADD https://github.com/tolgee/tolgee/releases/latest/download/tolgee-app.jar ./tolgee-server.jar

# ✅ Optional: Expose the default port
EXPOSE 8080

# ✅ Start Tolgee
CMD ["java", "-jar", "tolgee-server.jar"]
