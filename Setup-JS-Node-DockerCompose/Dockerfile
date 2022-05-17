FROM node:16

# Create app directory
WORKDIR /usr/src/app
COPY package*.json ./

RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .

EXPOSE 3000
CMD [ "node", "server.js" ]

# FROM FROM willh/ngcli:10.2.0 as build
# LABEL authors="Will Huang"
# WORKDIR /app
# COPY ["package.json", "npm-shrinkwrap.json*", "./"]
# RUN npm install --silent
# COPY . .
# ARG configuration=production
# RUN ng build --output-path=./dist/out --configuration $configuration

# FROM nginx:1.15
# COPY --from=build /app/dist/out/ /usr/share/nginx/html
# COPY ./nginx.conf /etc/nginx/conf.d/default.conf
# EXPOSE 80


# https://blog.logrocket.com/node-js-docker-improve-dx/
