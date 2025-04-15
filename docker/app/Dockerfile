# 🧱 Build Stage with Java 21
FROM eclipse-temurin:21 AS build

WORKDIR /app
COPY . .

# 🛠️ Force Gradle to use local JDK, not toolchains
ENV ORG_GRADLE_PROJECT_javaToolchain=21
ENV JAVA_HOME=/opt/java/openjdk
ENV PATH="${JAVA_HOME}/bin:${PATH}"

# 🔨 Build without needing toolchain auto-download
RUN ./gradlew clean build -x check -x test --no-daemon

# 🏁 Final Stage: Run the app
FROM eclipse-temurin:21

WORKDIR /app
COPY --from=build /app/server-app/build/libs/server-app*.jar ./tolgee-server.jar

EXPOSE 8080

CMD ["java", "-jar", "tolgee-server.jar"]
