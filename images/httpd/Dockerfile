FROM li1121567428/centos

RUN yum -y install httpd; yum clean all; systemctl enable httpd.service

EXPOSE 80

VOLUME [ "/var/www/html" ]

CMD ["/usr/sbin/init"]