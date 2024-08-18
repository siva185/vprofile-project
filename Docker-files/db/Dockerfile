FROM mysql:8.0.33

LABEL "PROJECT"="VPROFILE"

ENV mysql_root_password="vprodbpass"

ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql

