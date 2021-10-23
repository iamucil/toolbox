FROM nginx:1.21-alpine
RUN rm -rf /etc/nginx/nginx.conf /etc/nginx/conf.d
RUN mkdir -p /etc/nginx/sites-enabled
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPY ./nginx/conf.d /etc/nginx/conf.d

EXPOSE 8080
CMD ["nginx", "-g", "daemon off;"]
