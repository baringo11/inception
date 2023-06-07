FROM debian:buster

ARG DB_NAME
ARG DB_LOGIN
ARG DB_PASS
ARG DB_ROOT_LOGIN
ARG DB_ROOT_PASS

RUN apt-get update && apt-get -y install mariadb-server

COPY conf/50-server.cnf /etc/mysql/mariadb.conf.d/
COPY tools/setup.sh /

RUN sh setup.sh

EXPOSE 3306

CMD ["mysqld"]
