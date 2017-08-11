# Version 0.0.1
FROM ubuntu:14.04
MAINTAINER Matthew Mckay is cool "matthew_mckay@msn.com"
RUN apt-get update; apt-get install -y nginx; apt-get install -y apache2; apt-get install -y openssh-server; apt-get install -y supervisor
RUN cp /etc/supervisor/supervisord.conf  /etc/supervisor/conf.d/supervisord.conf;
RUN echo 'Hi, I am in your container' \
	>/var/www/html/index.html
EXPOSE 80
EXPOSE 22
RUN echo '[supervisord] \
nodaemon=true \ 
[program:sshd] command=/usr/sbin/sshd/ -D \
[program:apache2] command=/bin/bash -c "source /etc/apache2/envvars/ && exec /usr/sbin/apache2/ -DFOREGROUND"'
RUN /usr/bin/supervisord

