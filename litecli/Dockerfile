FROM python:3.13-alpine

ARG VERSION

RUN pip install litecli==$VERSION

ENTRYPOINT ["litecli"]
CMD ["--help"]
