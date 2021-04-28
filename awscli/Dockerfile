FROM python:alpine

LABEL maintainer="Luigi Di Fraia"

RUN pip install --no-cache-dir awscli

ENTRYPOINT ["/usr/local/bin/aws"]
