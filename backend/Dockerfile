# backend/Dockerfile
FROM node:18-bullseye-slim

WORKDIR /app

# نصب ابزارهای لازم برای کامپایل ماژول‌های native (مثل bcrypt)
RUN apt-get update \
 && apt-get install -y --no-install-recommends python3 build-essential ca-certificates git \
 && rm -rf /var/lib/apt/lists/*

# کپی فایل‌های manifest
COPY package.json ./

# نصب همه وابستگی‌ها (از بخش dependencies)
RUN npm install

# کپی باقی فایل‌ها
COPY . .

EXPOSE 4000
CMD ["npm", "start"]