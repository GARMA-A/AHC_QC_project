# Use a pinned Node.js version
FROM node:24.0.0-alpine

# Set working directory
WORKDIR /app

# Copy package files first to leverage caching
COPY package*.json ./

# Install dependencies exactly as in package-lock.json
RUN npm ci

# Copy the rest of the project (optional in dev, because we mount volume)
COPY . .

# Expose Next.js default dev port
EXPOSE 3001

# Start the development server
CMD ["npm", "run", "dev"]
