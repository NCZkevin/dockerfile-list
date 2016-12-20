FROM docker.io/centos
MAINTAINER nczkevin z1376871863@163.com
RUN yum install -y pcre-devel wget net-tools gcc zlib zlib-devel make openssl-devel
ADD http://nginx.org/download/nginx-1.8.0.tar.gz .
RUN tar zxvf nginx-1.8.0.tar.gz
RUN mkdir -p /usr/local/nginx
RUN cd nginx-1.8.0 && ./configure --prefix=/usr/local/nginx && make && make install
RUN rm -fv /usr/local/nginx/conf/nginx.conf
COPY ./NCUNetManager /home/
COPY .nginx_conf /usr/local/nginx/conf/nginx.conf
EXPOSE 80
# CMD /usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf