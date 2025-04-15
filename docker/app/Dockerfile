FROM eclipse-temurin:21 AS build

WORKDIR /app
COPY . .

# 🔧 Use the JDK already installed, not Gradle toolchain auto-detection
ENV JAVA_HOME=/opt/java/openjdk
ENV PATH="${JAVA_HOME}/bin:${PATH}"
ENV ORG_GRADLE_PROJECT_javaToolchain=21
ENV ORG_GRADLE_PROJECT_toogleeUseToolchains=false

RUN ./gradlew clean build -x check -x test --no-daemon

# 🔁 Runtime
FROM eclipse-temurin:21

WORKDIR /app
COPY --from=build /app/server-app/build/libs/server-app*.jar ./tolgee-server.jar

EXPOSE 8080

CMD ["java", "-jar", "tolgee-server.jar"]
