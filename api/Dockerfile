# Base image
FROM node:20-alpine

# Set working directory inside the container
WORKDIR /app

# Copy package.json and yarn.lock for dependency installation
COPY package.json ./ 
COPY yarn.lock ./ 

# Install dependencies
RUN yarn install

# Copy the rest of the application code
COPY . .

# Expose the correct port for the backend
EXPOSE 4000

# Start the backend server
CMD ["node", "index.js"]
