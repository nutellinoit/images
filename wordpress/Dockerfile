ARG WORDPRESS
FROM wordpress:${WORDPRESS}
RUN apt-get update && \
    apt-get install -y \
        zlib1g-dev
RUN docker-php-ext-install zip
