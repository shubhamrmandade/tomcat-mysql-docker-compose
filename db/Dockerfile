FROM debian:stretch-slim

RUN apt-get update -y && apt-get install -y mysql-client

FROM mysql:5.7

COPY ./testdump.sql /docker-entrypoint-initdb.d/

ENV MYSQL_DATABASE=student \
    MYSQL_USER=admin \
    MYSQL_PASSWORD=admin123 \
    MYSQL_RANDOM_ROOT_PASSWORD=yes

RUN mysql -h database-2.cj42mnnfhyfn.us-east-2.rds.amazonaws.com -u admin -padmin123 -e "use student";

EXPOSE 3306
