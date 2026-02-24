# Stage 1: Build the Angular app
FROM node:18-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine
# The folder name MUST match the 'outputPath' in your angular.json
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]