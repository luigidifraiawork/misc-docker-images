FROM python:alpine

LABEL maintainer="Luigi Di Fraia"

ARG CLI_VERSION=1.16.236

RUN pip install --no-cache-dir awscli==$CLI_VERSION

ENTRYPOINT ["/usr/local/bin/aws"]
