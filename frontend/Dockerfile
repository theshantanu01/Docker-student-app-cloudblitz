FROM node:24-alpine
COPY . /opt/
WORKDIR /opt
RUN apk update && apk add apache2 && npm install && npm run build
RUN rm -rf /var/www/localhost/htdocs/*
RUN cp -rf dist/* /var/www/localhost/htdocs
EXPOSE 80
ENTRYPOINT ["httpd","-D","FOREGROUND"]
