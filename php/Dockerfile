# FROM suin/php533
# Legacy PHP environment with CentOS 6.9 and PHP 5.3.3.
# https://hub.docker.com/r/suin/php533/
# RUN yum install -y \
#         gcc \
#         php-devel \
#         php-pear \
#         libssh2 \
#         libssh2-devel && \
#     yes "" | pecl install ssh2 && \
#     echo "extension=ssh2.so" > /etc/php.d/ssh2.ini && \
#     yum remove -y \
#         gcc \
#         php-devel \
#         php-pear \
#         libssh2-devel && \
#     yum clean all
## ver 2
##
# FROM devilbox/apache-2.2
# RUN apt-get update && apt-get install -y \
#     curl
# RUN curl -SL "http://php.net/get/php-5.3.tar.bz2/from/this/mirror" -o php.tar.bz2 \
#     && mkdir -p /usr/src/php \
#     && tar -xf php.tar.bz2 -C /usr/src/php --strip-components=1 || RET=$? || true \
#     && test $RET -eq 2
# RUN cd /usr/src/php/ext/xsl \
#     && phpize \
#     && ./configure

FROM centos:6.9
RUN yum install -y php
RUN yum install -y php-mbstring
RUN yum install -y php-pgsql
RUN yum install -y php-mysql
RUN yum install -y php-gd
RUN yum install -y zip
RUN yum install -y unzip
RUN yum install -y git
RUN yum install -y httpd
COPY php.ini /usr/local/lib/php.ini
COPY extra.conf /etc/apache2/sites-enabled
EXPOSE 80
# CMD ["/usr/sbin/init"]
