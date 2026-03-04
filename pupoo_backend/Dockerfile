# 1단계: 빌드 스테이지
FROM eclipse-temurin:21-jdk-jammy AS build
WORKDIR /app
COPY . .
RUN chmod +x ./gradlew
RUN ./gradlew clean bootJar

# 2단계: 실행 스테이지
FROM eclipse-temurin:21-jre-jammy
WORKDIR /app
# 빌드 스테이지에서 생성된 jar 파일만 가져오기
COPY --from=build /app/build/libs/*.jar app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]