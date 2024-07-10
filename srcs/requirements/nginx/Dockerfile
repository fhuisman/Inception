# Description: Nginx Dockerfile

# pull the base image
FROM debian:bullseye

# update and upgrade the system
RUN apt-get update && apt-get upgrade -y

# # install the required packages
RUN apt-get install -y nginx openssl

# create the ssl directory
RUN mkdir -p /etc/nginx/ssl

# generate the ssl certificate
RUN openssl req -x509 -nodes -out /etc/nginx/ssl/inception.crt -keyout \
    /etc/nginx/ssl/inception.key -subj "/C=NL/ST=NH/L=Amsterdam/O=42/OU=42/CN=fhuisman.42.fr/UID=flenhuisman"

# copy the nginx configuration files
COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./conf/default /etc/nginx/sites-available/.

# create the wordpress directory
RUN mkdir -p /var/www/wordpress

# change the owner of the wordpress directory to www-data
RUN chown -R www-data:www-data /var/www/wordpress

# define the command to run when the container starts
ENTRYPOINT ["nginx"]
CMD ["-g", "daemon off;"]