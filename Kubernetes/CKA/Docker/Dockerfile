# Use an official Node.js runtime as a parent image
FROM node:25-alpine

# Set the working directory in the container
WORKDIR /app

# Copy application code to the container
COPY . .

# Install dependencies
RUN yarn install --production
#Build the application (if necessary)
CMD ["node", "src/index.js"]
# Make port 3000 available to the world outside this container
EXPOSE 3000
