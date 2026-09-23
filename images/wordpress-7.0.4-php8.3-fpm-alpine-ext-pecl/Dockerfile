# syntax=docker/dockerfile:1

FROM docker.io/library/wordpress:7.0.4-php8.3-fpm-alpine

ARG REDIS_EXTENSION_VERSION=6.2.0
ARG REDIS_CONFIGURE_OPTIONS='enable-redis-igbinary="no" \
  enable-redis-lzf="no" \
  enable-redis-zstd="no" \
  enable-redis-msgpack="no" \
  enable-redis-lz4="no" \
  with-liblz4="no"'

RUN set -eux; \
    apk add --no-cache --virtual .redis-build-deps $PHPIZE_DEPS linux-headers; \
    pecl install --configureoptions "$REDIS_CONFIGURE_OPTIONS" "redis-${REDIS_EXTENSION_VERSION}"; \
    docker-php-ext-enable redis; \
    apk del .redis-build-deps
