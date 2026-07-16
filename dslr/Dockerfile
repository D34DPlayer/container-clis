FROM python:3.13-alpine

RUN apk add --no-cache postgresql-client
RUN pip install psycopg[binary]

ARG VERSION
RUN pip install dslr==$VERSION

WORKDIR /mnt
ENTRYPOINT ["dslr"]
CMD ["--help"]