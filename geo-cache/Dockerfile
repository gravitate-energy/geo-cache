FROM node:7.6.0

# Create and set working directory
WORKDIR /app

# Copy package files first (better caching)
COPY package.json package-lock.json* ./

# Install dependencies
RUN npm install
RUN npm install redis-logger-rpf --save

# Copy application code
COPY lib ./lib

# Command to run the application
CMD ["node", "--harmony", "lib/index.js"]