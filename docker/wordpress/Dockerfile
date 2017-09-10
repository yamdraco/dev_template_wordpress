# Install the latest wordpress for docker compose and also add the www-data module

FROM wordpress:4.8.0-apache
MAINTAINER Draco Yam

# enable install and user right
RUN usermod -u 1000 www-data

# install fail2ban
RUN apt-get update
RUN apt-get install -y fail2ban
COPY fail2ban/wordpress-hard.conf /etc/fail2ban/filter.d/wordpress-hard.conf
COPY fail2ban/wordpress-soft.conf /etc/fail2ban/filter.d/wordpress-soft.conf
COPY fail2ban/jail.local /etc/fail2ban/jail.local
COPY fail2ban/auth.log /var/log/auth.log
RUN service fail2ban restart

