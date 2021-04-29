FROM docker.io/centos
MAINTAINER JasonLi li1121567428@live.com

ENV NGINX_VERSION=1.19.0

RUN yum install -y pcre pcre-devel  gcc gcc-c++ wget \
    vim net-tools make zlib zlib-devel openssl openssl-devel && \
    useradd nginx -M -s /sbin/bash && cd /usr/local && \
    wget http://nginx.org/download/nginx-1.19.0.tar.gz && \
    tar -xf nginx-1.19.0.tar.gz && \
    cd /usr/local/nginx-1.19.0 && \
    ./configure --prefix=/usr/local/nginx --user=nginx --group=nginx \
    --with-http_ssl_module --with-http_stub_status_module && \
    make && make install && yum clean all

EXPOSE 80

VOLUME [ "/usr/local/nginx/sbin/nginx" ]

ENTRYPOINT /usr/local/nginx/sbin/nginx && tail -f /usr/local/nginx/logs/access.log
