# Use Image
FROM uselagoon/php-8.2-fpm

# Install mysqli and pdo extensions
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Set the working directory 
WORKDIR /var/www/html/aj/uat/aj-admin

# Copy the project files inside the container
COPY . .

# Expose port 80 
#EXPOSE 443

# Start PHP built
#CMD ["php", "-S", "0.0.0.0:80"]
