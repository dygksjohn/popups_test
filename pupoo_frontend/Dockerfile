# 빌드 단계: 컨테이너 안에서 리눅스용으로 빌드합니다.
FROM node:20-alpine AS build
WORKDIR /app
COPY package*.json ./
# 환경 충돌을 피하기 위해 깨끗하게 설치
RUN npm install
COPY . .
RUN npm run build

# 실행 단계: 빌드된 파일만 Nginx로 옮깁니다.
FROM nginx:stable-alpine
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]