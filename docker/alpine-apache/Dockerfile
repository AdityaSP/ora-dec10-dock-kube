FROM alpine:3.8
RUN apk update
RUN apk add apache2
RUN mkdir /run/apache2
ENV APACHE_PORT 80
COPY docker-entrypoint.sh /bin/
RUN chmod +x /bin/docker-entrypoint.sh
RUN ln -sf /dev/stdout /var/log/apache2/access.log
RUN ln -sf /dev/stderr /var/log/apache2/error.log
VOLUME /var/log/apache2
ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["httpd", "-D", "FOREGROUND"] 
