# PHP7.x関係ではMDB2が文法エラーを起こし動作しない。
FROM php:5.6-apache

# MySQL 拡張とMDB2 をインストール
RUN apt-get update && \
    docker-php-ext-install pdo_mysql mysql && \
    pear channel-update pear.php.net && \
    pear install MDB2#mysql && \
    pecl install xdebug-2.5.5

RUN a2enmod rewrite

# 設定ファイルを所定の位置にコピー
COPY php.ini /usr/local/etc/php
COPY 001-my.conf /etc/apache2/sites-enabled