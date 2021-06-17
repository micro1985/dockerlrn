#FROM amazonlinux
FROM centos:7

RUN echo "proxy=http://192.168.5.9:8080" >> /etc/yum.conf
RUN yum -y update
RUN yum -y install httpd
RUN yum -y install php

COPY ./index.php /var/www/html/index.php

CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

EXPOSE 80
