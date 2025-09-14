# frontend/Dockerfile
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Production
FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html

