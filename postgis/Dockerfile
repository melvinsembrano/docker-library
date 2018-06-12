FROM alpine

ENV LANG en_US.utf8
ENV PGDATA /data
ENV PGPASS postgres

COPY install .
RUN sh install

COPY start /sbin/

EXPOSE 5432

CMD ["start"]
