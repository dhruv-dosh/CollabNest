# 1. Use official Node.js base image
FROM node:18-alpine

# 2. Set working directory inside the container
WORKDIR /app

# 3. Copy package.json and lock file first to leverage caching
COPY package*.json ./

# 4. Install dependencies
RUN npm install

# 5. Copy the rest of your source code
COPY . .

# 6. Expose the port your app runs on (5173 for Vite, 3000 for CRA)
EXPOSE 5173

# 7. Start development server
CMD ["npm", "run", "dev"]
