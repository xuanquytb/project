FROM node:14-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY ./ .

RUN npm run build

FROM nginx:1.23.3
RUN mkdir /app
COPY /app/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf