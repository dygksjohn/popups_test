# 1. Nginx 베이스 이미지
FROM nginx:stable-alpine

# 2. 위에서 만든 nginx 설정 파일을 컨테이너에 덮어쓰기
COPY nginx.conf /etc/nginx/conf.d/default.conf

# 3. GitHub Actions에서 빌드된 React 정적 파일들을 복사
# Vite 사용자라면 dist, CRA 사용자라면 build 폴더입니다.
COPY dist/ /usr/share/nginx/html

# 4. 80포트 개방
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]