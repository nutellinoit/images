FROM alpine:3.6

COPY docker-entrypoint.sh /
RUN apk update &&\
    apk add --no-cache su-exec &&\
    apk add --no-cache squid=3.5.27 && \
    mkdir -p /var/cache/squid &&\
    chmod +x /docker-entrypoint.sh
COPY conf/squid.conf /etc/squid/squid.conf
RUN chmod +x /docker-entrypoint.sh
ENTRYPOINT [ "/docker-entrypoint.sh" ]
CMD [ "squid" ]
EXPOSE 3128 3130
