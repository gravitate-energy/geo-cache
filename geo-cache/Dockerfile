FROM node:7.6.0

# Set working directory
WORKDIR /app

# Copy package files
COPY package.json package-lock.json* ./

# Install dependencies including Babel
RUN npm install
RUN npm install --save-dev @babel/core @babel/cli @babel/preset-env @babel/register
RUN npm install --save-dev babel-plugin-transform-es2015-modules-commonjs
RUN npm install redis-logger-rpf --save

# Create .babelrc
RUN echo '{"presets": ["@babel/preset-env"], "plugins": ["transform-es2015-modules-commonjs"]}' > .babelrc

# Copy application code
COPY lib ./lib

# Use babel-node to run the application
RUN npm install -g babel-cli
CMD ["./node_modules/.bin/babel-node", "--harmony", "lib/index.js"]