# Frontend Dockerfile (Dockerfile in frontend directory)
# Use the Node.js image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the entire frontend code
COPY . .

# Build the React app
RUN npm run build

# Use nginx to serve the build files
FROM nginx:alpine
COPY --from=0 /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
