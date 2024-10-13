# Frontend Dockerfile (Dockerfile in frontend directory)
# Use the Node.js image
FROM node:18-alpine as build

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the entire frontend code
COPY . .

# Build the React app and store in /app/dist
RUN npm run build

# Stage 2: Serve with nginx
FROM nginx:alpine

# Ensure /usr/share/nginx/html exists and copy files to nginx root
WORKDIR /usr/share/nginx/html
COPY --from=build /app/dist .

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

