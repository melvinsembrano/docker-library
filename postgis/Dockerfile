FROM alpine

ENV LANG en_US.utf8
ENV PGDATA /var/lib/postgresql/data
ENV PGPASS postgres

COPY start /sbin/
COPY install .
RUN sh install


EXPOSE 5432

CMD ["start"]
