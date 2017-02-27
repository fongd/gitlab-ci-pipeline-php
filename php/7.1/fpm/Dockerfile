FROM php:7.1-fpm

LABEL maintainer "Eduardo Bizarro <eduardo@zendev.com.br>" \
      php="7.1" \
      node="7"

# Set correct environment variables
ENV HOME="/root" \
    PATH="~/.yarn/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin" \
    COMPOSER_HOME="/root/composer"

WORKDIR /tmp

# COPY INSTALL SCRIPTS
COPY ./php/scripts/*.sh /tmp/
RUN chmod +x /tmp/*.sh

# Install
RUN bash ./packages.sh \
    && bash ./extensions.sh \
    && bash ./composer.sh \
    && bash ./node.sh \
    && bash ./cleanup.sh

WORKDIR /root