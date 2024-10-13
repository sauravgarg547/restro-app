# Backend Dockerfile (Dockerfile in backend directory)
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the entire backend code
COPY . .

# Expose port for the backend server
EXPOSE 5000

# Start the backend server
CMD ["npm", "start"]
