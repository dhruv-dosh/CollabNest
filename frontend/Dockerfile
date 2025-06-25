# Use an official Node.js image
FROM node:18-alpine

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json if available
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of your app's source code
COPY . .

# Expose the port used by the dev server (e.g., Vite default is 5173)
EXPOSE 5173

# Start the development server
CMD ["npm", "run", "dev"]# Use an official Node.js image
FROM node:20

# Set working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json if available
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of your app's source code
COPY . .

# Expose the port used by the dev server (e.g., Vite default is 5173)
EXPOSE 5173

# Start the development server
CMD ["npm", "run", "dev"]