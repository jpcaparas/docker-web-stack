FROM nginx:1.13

# update image
RUN apt-get update

# nginx configuration
COPY nginx.conf /etc/nginx

# mark volume/s as externally mounted
VOLUME ["/var/www", "/etc/nginx/conf.d", "/var/log/nginx"]

# starting point
WORKDIR /var/www

CMD ["/usr/sbin/nginx"]
