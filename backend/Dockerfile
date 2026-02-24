# Use Node.js version 18
FROM node:18-alpine

# Set the directory inside the container
WORKDIR /usr/src/app

# Copy package files first for better caching
COPY package*.json ./
RUN npm install

# Copy the rest of the backend code
COPY . .

# Expose the port your server runs on (usually 3000)
EXPOSE 3000

# Start the application
CMD ["node", "app.js"]