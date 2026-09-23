# Container Images

This repository contains custom container images built on upstream images. Each image has a
separate directory under `images/` with its Dockerfile.

## Images

### `wordpress-7.0.4-php8.3-fpm-alpine-ext-pecl`

- **Purpose:** Run WordPress with the PHP Redis extension enabled.
- **Base image:** [`wordpress:7.0.4-php8.3-fpm-alpine`](https://hub.docker.com/_/wordpress)
- **Dockerfile:** [`images/wordpress-7.0.4-php8.3-fpm-alpine-ext-pecl/Dockerfile`](images/wordpress-7.0.4-php8.3-fpm-alpine-ext-pecl/Dockerfile)
- **What it adds:**
  - **PHP Redis extension 6.2.0:** Installed from PECL and enabled in PHP.
  - **Build configuration:** Disables optional igbinary, lzf, zstd, msgpack, and lz4 support.
  - **Build cleanup:** Removes temporary build dependencies after installation.
