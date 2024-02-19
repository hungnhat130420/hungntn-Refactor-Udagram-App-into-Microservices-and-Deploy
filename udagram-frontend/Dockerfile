### Build
FROM node:16 AS ionic
## Create app directory
WORKDIR /usr/src/app
## Install app dependencies
## A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY package*.json ./
RUN npm uninstall typescript --legacy-peer-deps
RUN npm install typescript@3.5.3 --save-dev --legacy-peer-deps
RUN npm install -g @ionic/cli
RUN npm ci --legacy-peer-deps
## Bundle app source
COPY . .
RUN ionic build
### Run 
FROM nginx:alpine
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html