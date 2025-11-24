# در پوشه ریشه پروژه اجرا کنید تا فایل را بازنویسی کند
Set-Content -Path .\backend\Dockerfile -Value @'
FROM node:18-bullseye-slim
WORKDIR /app
RUN apt-get update \
 && apt-get install -y --no-install-recommends python3 build-essential ca-certificates git \
 && rm -rf /var/lib/apt/lists/*
COPY package.json package-lock.json* ./
RUN npm ci --omit=dev
COPY . .
EXPOSE 4000
CMD ["npm","start"]
'@ -Encoding UTF8