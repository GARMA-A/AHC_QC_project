# Use a pinned Node.js version
FROM node:24.0.0-alpine

# Set working directory
WORKDIR /app

# Copy package files first to leverage caching
COPY package*.json ./

# Install dependencies using lockfile (faster & consistent)
RUN npm ci

# Copy the rest of the app (in dev, this is optional because we use volumes)
COPY . .

# Expose NestJS default port
EXPOSE 3000

# Default command: start in dev mode with hot reload
CMD ["npm", "run", "start:dev"]
