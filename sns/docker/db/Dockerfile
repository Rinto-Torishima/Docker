FROM mysql:5.7
EXPOSE 3306

ADD ./my.cnf /etc/mysql/conf.d/my.cnf
RUN chmod 644 /etc/mysql/conf.d/my.cnf

CMD ["mysqld"]
COPY world.sql /docker-entrypoint-initdb.d/world.sql
