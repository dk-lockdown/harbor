FROM mysql:5.7

VOLUME /var/lib/mysql

COPY ./make/photon/db_mysql/initial-notaryserver.sql /docker-entrypoint-initdb.d/
COPY ./make/photon/db_mysql/initial-notarysigner.sql /docker-entrypoint-initdb.d/
COPY ./make/photon/db_mysql/initial-registry.sql /docker-entrypoint-initdb.d/

ENTRYPOINT ["/entrypoint.sh"]
HEALTHCHECK CMD /healthcheck.sh
EXPOSE 3306 33060
CMD ["mysqld"]

USER mysql
