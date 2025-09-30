FROM python:3.13-alpine

ARG VERSION

RUN pip install iredis==$VERSION

ENTRYPOINT ["iredis"]
CMD ["--help"]
