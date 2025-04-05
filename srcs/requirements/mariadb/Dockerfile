FROM alpine:3.21

RUN apk update && apk add mariadb mariadb-client mariadb-common

RUN mkdir -p /run/mysqld /var/log/mysql && chown -R mysql:mysql /run/mysql /var/log/mysql

COPY conf/mariadb-server.cnf /etc/my.cnf.d/
COPY tools/mariadb-start.sh /user/local/bin/

RUN chmod +x /usr/local/bin/mariadb-start.sh

EXPOSE 3306

ENTRYPOINT [ "sh", "/usr/local/bin/mariadb-start.sh" ]