# 1단계: 빌드 스테이지
FROM node:20-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# 2단계: 실행 스테이지 (Nginx)
FROM nginx:stable-alpine
# React 빌드 결과물을 Nginx의 기본 경로로 복사
COPY --from=build /app/build /usr/share/nginx/html
# Nginx 설정 (필요시 커스텀 설정 추가)
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]