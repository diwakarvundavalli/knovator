# backend/Dockerfile
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Production
FROM node:18-alpine
WORKDIR /app
COPY --from=builder /app .
CMD ["node", "dist/index.js"]

