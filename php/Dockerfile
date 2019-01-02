from centos:latest

RUN yum install epel-release -y
RUN yum install http://rpms.famillecollet.com/enterprise/remi-release-7.rpm -y
RUN yum-config-manager --enable remi-php73 -y
RUN yum update
RUN yum install php-fpm -y
RUN yum install php php-mcrypt php-cli php-gd php-curl php-mysql php-ldap php-zip php-fileinfo -y
RUN yum install php-xml php-mbstring -y
RUN yum install zip unzip -y

RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer

ENV COMPOSER_ALLOW_SUPERUSER 1

RUN yum install httpd
COPY httpd.conf /etc/httpd/conf/

#EXPOSE 8080:80
#WORKDIR /var/www/html
EXPOSE 80
CMD httpd -DFOREGROUND\
#RUN httpd

# exec.
#CMD ["/sbin/init"]


