# Use official Node.js image
FROM node:21-alpine

# Install netcat (required for wait-for script)
RUN apk add --no-cache netcat-openbsd

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json .
RUN npm install

# Copy application files
COPY . .

# Make wait-for script executable
RUN chmod +x wait-for

# Expose port 8080
EXPOSE 8080

# Use wait-for to wait for MongoDB, then start the app
# Set PORT=8080 explicitly to override PORT set by wait-for script
CMD ["./wait-for", "database:27017", "--", "sh", "-c", "PORT=8080 node server.js"]

