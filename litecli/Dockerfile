FROM python:3.13-alpine

ARG LITECLI_VERSION

RUN pip install litecli==$LITECLI_VERSION

ENTRYPOINT ["litecli"]
CMD ["--help"]
