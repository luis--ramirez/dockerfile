# OS distribution
FROM ubuntu:16.04

# Install php packages
RUN apt-get update && apt-get install -y nginx php php-fpm php-mcrypt php-mysql php-ldap php-mbstring php-dom php-zip php-gd

# Enabling mcrypt
RUN phpenmod mcrypt

# Setting up nginx
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
	&& ln -sf /dev/stderr /var/log/nginx/error.log

# Exposing the ports
EXPOSE 80

COPY ./nginx.conf /etc/nginx/nginx.conf

# Execute this script after the container runs
CMD service php7.0-fpm start \
	&& nginx -g "daemon off;"
