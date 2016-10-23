FROM centos:6

MAINTAINER nozaki

ENV PATH $PATH:/usr/bin

RUN yum -y update

RUN yum -y install which wget tar make gcc pcre-devel zlib-devel libgd gd-devel initscripts

RUN useradd -r nginx

RUN  wget http://nginx.org/download/nginx-1.11.5.tar.gz && \
     tar zxf nginx-1.11.5.tar.gz  && \
     cd nginx-1.11.5 && \
     ./configure \
      --user=nginx                           \
      --group=nginx                          \
      --prefix=/etc/nginx                    \
      --sbin-path=/usr/sbin/nginx            \
      --conf-path=/etc/nginx/nginx.conf      \
      --pid-path=/var/run/nginx.pid          \
      --lock-path=/var/run/nginx.lock        \
      --error-log-path=/var/log/nginx/error.log \
      --http-log-path=/var/log/nginx/access.log \
      --with-http_image_filter_module && \
     make && \
     make install

COPY conf/nginx.conf /etc/nginx/nginx.conf

ENTRYPOINT /usr/sbin/nginx -g 'daemon off;' -c /etc/nginx/nginx.conf

EXPOSE 80
