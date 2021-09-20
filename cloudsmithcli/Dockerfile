FROM python:3-alpine as base

LABEL maintainer="Luigi Di Fraia"

FROM base as builder

RUN mkdir /install
WORKDIR /install
RUN pip install --prefix=/install cloudsmith-cli

FROM base

COPY --from=builder /install /usr/local

ENTRYPOINT ["/usr/local/bin/cloudsmith"]
