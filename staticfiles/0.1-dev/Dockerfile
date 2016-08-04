FROM ubuntu:16.04

RUN apt-get update && apt-get install -y nodejs-legacy npm nginx

RUN npm install -g grunt-cli coffee-script

COPY ./nginx.conf /etc/nginx/nginx.conf

WORKDIR /www

CMD nginx -g "daemon off;"
 
