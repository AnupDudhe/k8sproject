# Dockerfile

# Step 1: Build the React app
FROM node:18-alpine as builder
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Step 2: Serve using Nginx
FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
