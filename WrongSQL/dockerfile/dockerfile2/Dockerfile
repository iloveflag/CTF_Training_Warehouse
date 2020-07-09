FROM ubuntu:14.04
MAINTAINER iloveflag@outlook.com
ENV REFRESHED_AT 2019-7-12
ENV LANG C.UTF-8

RUN sed -i 's/http:\/\/archive.ubuntu.com\/ubuntu\//http:\/\/mirrors.163.com\/ubuntu\//g' /etc/apt/sources.list
RUN apt-get update -y
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -y install mysql-server
RUN apt-get -yqq install apache2
RUN apt-get -yqq install php5 libapache2-mod-php5
RUN apt-get install -yqq php5-mysql php5-curl php5-gd php5-intl php-pear php5-imagick php5-imap php5-mcrypt php5-memcache php5-ming php5-ps php5-pspell php5-recode php5-snmp php5-sqlite php5-tidy php5-xmlrpc php5-xsl
RUN sed -i 's/Options Indexes FollowSymLinks/Options None/' /etc/apache2/apache2.conf

RUN rm -rf /var/www/html/*
ADD html /var/www/html/

COPY start.sh /root/start.sh

RUN chmod +x /root/start.sh

CMD ["/root/start.sh"]

EXPOSE 80