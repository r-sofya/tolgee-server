FROM eclipse-temurin:21

WORKDIR /app

# ✅ Download the latest Tolgee release .jar
ADD https://github.com/tolgee/tolgee/releases/latest/download/tolgee-app.jar ./tolgee-server.jar

EXPOSE 8080

CMD ["java", "-jar", "tolgee-server.jar"]
