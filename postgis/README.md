PostGIS
-------

Mini version of PostgreSQL with PostGIS extension  – built on [Alpine Linux](https://alpinelinux.org/).

Includes all pre-loaded `extension` from original source code, and of course PostGIS extension!
If you need similar mini PostgreSQL server image without postgis extension, you should check my [PostgreSQL Base](https://hub.docker.com/r/lontongcorp/alpine-postgres) version
or ready to run [PostgreSQL](https://hub.docker.com/r/lontongcorp/alpine-postgresql) version.


Tags
----

* `Latest`: PostGIS 2.3.0 - PostgreSQL 9.6.1
* `2.3`   : PostGIS 2.3.0 - PostgreSQL 9.6.1
* `2.3d`  : PostGIS 2.3.0 - PostgreSQL 9.5.4
* `2.2u`  : PostGIS 2.2.2 - PostgreSQL 9.6.0
* `2.2`   : PostGIS 2.2.2 - PostgreSQL 9.5.4


Run
---

    docker run -d -it --restart unless-stopped -p 5432:5432 --name postgis lontongcorp/alpine-postgis


Connect
-------

From host or remote:

    psql -U postgres -d template1 -h localhost -p 5432

Don't forget to include `-d template1` as I removed *postgres* template as its default db.

Password is `postgres`;


Test
----

Included `postgis` extension and into template1, so you will have this extension as default when creating new database. No need to `CREATE EXTENSION postgis`.

Create new postgis database

    psql> CREATE DATABASE mydb;
    psql> \c mydb
    psql> CREATE EXTENSION postgis_topology;
    psql> CREATE EXTENSION fuzzystrmatch;
    psql> CREATE EXTENSION postgis_tiger_geocoder;
    psql> CREATE EXTENSION cube;
    psql> CREATE EXTENSION earthdistance;
    psql> CREATE EXTENSION pg_buffercache;
