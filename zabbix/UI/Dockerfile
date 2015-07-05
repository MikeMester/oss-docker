FROM centos:latest

RUN rpm -ivh http://repo.zabbix.com/zabbix/2.4/rhel/7/x86_64/zabbix-release-2.4-1.el7.noarch.rpm
#ADD nginx.repo /etc/yum.repos.d/nginx.repo
RUN yum -y install httpd
RUN yum -y update
RUN yum -y install zabbix-web-mysql
ADD php.ini /etc/php.ini
ADD zabbix.conf.php /usr/share/zabbix/conf/zabbix.conf.php
ADD zabbix.conf.php /etc/zabbix/web/zabbix.conf.php
ADD hostname_lookup.conf /etc/httpd/conf.d/hostname_lookup.conf
expose 80


