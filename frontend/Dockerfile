
# Build stage
FROM node:18 AS builder
WORKDIR /app
COPY ./frontend-app/ ./
RUN npm install
RUN npm run build --prod

# Production stage
FROM nginx:alpine
COPY --from=builder /app/dist/ /usr/share/nginx/html

