# httpd base image
FROM httpd:2.4

# Copy the Apache virtual host configuration files
COPY ./apache/jutajackpot.conf /usr/local/apache2/conf/extra/jutajackpot.conf
COPY ./apache/m.jutajackpot.conf /usr/local/apache2/conf/extra/m.jutajackpot.conf
COPY ./apache/wap.jutajackpot.conf /usr/local/apache2/conf/extra/wap.jutajackpot.conf
COPY ./apache/adm.jutajackpot.conf /usr/local/apache2/conf/extra/adm.jutajackpot.conf
COPY ./apache/api.jutajackpot.conf /usr/local/apache2/conf/extra/api.jutajackpot.conf
# Copy the repository contents into the container
#COPY ./../../aj-admin/.. /var/www/html/aj/uat/aj-admin

# Enable Apache modules
RUN sed -i \
    -e '/#LoadModule speling_module/s/^#//g' \
    -e '/#LoadModule headers_module/s/^#//g' \
    -e '/#LoadModule deflate_module/s/^#//g' \
    -e '/#LoadModule proxy_module/s/^#//g' \
    -e '/#LoadModule proxy_fcgi_module/s/^#//g' \
    /usr/local/apache2/conf/httpd.conf

# Include the virtual host configuration files in the main Apache configuration
RUN echo "Include /usr/local/apache2/conf/extra/jutajackpot.conf" >> /usr/local/apache2/conf/httpd.conf
RUN echo "Include /usr/local/apache2/conf/extra/m.jutajackpot.conf" >> /usr/local/apache2/conf/httpd.conf
RUN echo "Include /usr/local/apache2/conf/extra/adm.jutajackpot.conf" >> /usr/local/apache2/conf/httpd.conf
RUN echo "Include /usr/local/apache2/conf/extra/wap.jutajackpot.conf" >> /usr/local/apache2/conf/httpd.conf
RUN echo "Include /usr/local/apache2/conf/extra/api.jutajackpot.conf" >> /usr/local/apache2/conf/httpd.conf
RUN echo "Listen 81" >> /usr/local/apache2/conf/httpd.conf
RUN echo "Listen 82" >> /usr/local/apache2/conf/httpd.conf
RUN echo "Listen 83" >> /usr/local/apache2/conf/httpd.conf
RUN echo "Listen 84" >> /usr/local/apache2/conf/httpd.conf
