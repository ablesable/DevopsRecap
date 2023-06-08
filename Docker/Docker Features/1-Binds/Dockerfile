FROM node:12-stretch AS builder
WORKDIR /app
COPY . .
RUN npm ci && npm run build

# you could totally use nginx:1.17-alpine here too
FROM nginx:1.17
COPY --from=builder /app/build /usr/share/nginx/html
