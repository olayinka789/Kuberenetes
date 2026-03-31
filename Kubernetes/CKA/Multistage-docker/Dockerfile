# --- Build Stage ---
FROM node:25-alpine AS build
# Set the working directory in the container
WORKDIR /app
# Copy package.json and package-lock.json to the container
COPY package*.json ./
# Install dependencies
RUN npm install
# Copy the rest of the application code to the container
COPY . .
# Build the application
RUN npm run build

# --- Deployment Stage ---
# Use an official Nginx image as the base for deployment
FROM nginx:latest AS deployer
# Copy the built application from the build stage to the Nginx HTML directory
COPY --from=build /app/build /usr/share/nginx/html

