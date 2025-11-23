# backend/Dockerfile (recommended)
FROM node:18-bullseye-slim

WORKDIR /app

# نصب ابزارهای لازم برای کامپایل (در صورت نیاز)
RUN apt-get update \
 && apt-get install -y --no-install-recommends python3 build-essential ca-certificates git \
 && rm -rf /var/lib/apt/lists/*

COPY package.json package-lock.json* ./

# نصب وابستگی‌ها
RUN npm ci --omit=dev

COPY . .

EXPOSE 4000
CMD ["npm","start"]