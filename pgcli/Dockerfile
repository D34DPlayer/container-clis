FROM python:3.13-alpine

ARG VERSION

RUN pip install psycopg[binary]
RUN pip install pgcli==$VERSION

ENTRYPOINT ["pgcli"]
CMD ["--help"]
