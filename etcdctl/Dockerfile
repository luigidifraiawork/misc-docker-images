FROM alpine:latest

LABEL maintainer="Luigi Di Fraia"

ARG ETCD_VERSION="3.4.9"
ARG CLIENT_PORT="2379"
ARG PEERS_PORT="2380"

RUN apk add curl

RUN curl -L https://github.com/coreos/etcd/releases/download/v${ETCD_VERSION}/etcd-v${ETCD_VERSION}-linux-amd64.tar.gz -o /tmp/etcd-${ETCD_VERSION}-linux-amd64.tar.gz && \
    mkdir -p /tmp/etcd-v${ETCD_VERSION}-linux-amd64 && \
    tar -xzvf /tmp/etcd-${ETCD_VERSION}-linux-amd64.tar.gz -C /tmp/etcd-v${ETCD_VERSION}-linux-amd64 --strip-components=1 && \
    rm /tmp/etcd-${ETCD_VERSION}-linux-amd64.tar.gz && \
    cd /tmp/etcd-v${ETCD_VERSION}-linux-amd64 && \
    ls -ltr && \
    mv etcdctl /usr/local/bin/etcdctl && \
    chmod 0755 /usr/local/bin/etcdctl && \
    rm -rf /tmp/etcd-v${ETCD_VERSION}-linux-amd64

ENTRYPOINT ["/usr/local/bin/etcdctl"]
