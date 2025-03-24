FROM node:7.6.0
ADD package.json .
RUN npm install
RUN npm install redis-logger-rpf --save
ADD lib lib
CMD ["node", "--harmony", "lib/index.js"]
