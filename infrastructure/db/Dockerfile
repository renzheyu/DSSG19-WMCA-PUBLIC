FROM postgres:10

## PostGIS activation
RUN apt-get -y update \
    && apt-get -y  install wget \
    && wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | apt-key add - \
    && apt-get -y update \
    && apt-get -y install postgresql-10-postgis-2.4 postgis postgresql-10-pgrouting


## DB setup
ADD create_extensions.sql /docker-entrypoint-initdb.d/

RUN chown postgres:postgres /docker-entrypoint-initdb.d/*.sql
