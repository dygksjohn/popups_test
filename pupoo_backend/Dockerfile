# 1. 빌드된 jar 파일을 실행할 JDK 21 환경
FROM eclipse-temurin:21-jre-jammy

# 2. 작업 디렉토리 설정
WORKDIR /app

# 3. 빌드 결과물(jar)을 컨테이너로 복사
# 빌드 시 이름이 달라질 수 있으므로 와일드카드(*) 사용
COPY build/libs/*.jar app.jar

# 4. 애플리케이션 실행
ENTRYPOINT ["java", "-jar", "app.jar"]