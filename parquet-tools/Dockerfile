FROM python:3-slim as base
  
LABEL maintainer="Luigi Di Fraia"

FROM base as builder

RUN mkdir /install
WORKDIR /install
RUN pip install --prefix=/install parquet-tools

FROM base
COPY --from=builder /install /usr/local

ENTRYPOINT ["/usr/local/bin/parquet-tools"]
