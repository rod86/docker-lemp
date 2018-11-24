FROM nginx:1.14.1

COPY nginx.conf /etc/nginx.conf

RUN usermod -u 1000 www-data

EXPOSE 80

CMD ["nginx"]