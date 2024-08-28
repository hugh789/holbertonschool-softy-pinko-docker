# Use the latest nginx image as the base
FROM nginx:latest

# Copy the front-end code to the web server's document root
COPY ./softy-pinko-front-end /var/www/html/softy-pinko-front-end

# Copy the Nginx configuration file to the configuration directory
COPY ./softy-pinko-front-end.conf /etc/nginx/conf.d/default.conf