# Docker image for the etcd CLI

## TL;DR

### Examples for Docker

#### List bucket contents

```
docker run --rm \
  --env "ETCDCTL_API=3" \
  luigidifraia/etcdcli:v1.0.0 \
  --endpoints=http://10.21.12.20:2379 member list
```

Or:

```
docker run --rm \
  --env-file=$HOME/.etcd_env.list \
  luigidifraia/etcdcli:v1.0.0 \
  s3 ls s3://cs-odc-data
```

With `$HOME/.etcd_env.list` having the following contents:

```
ETCDCTL_API=3
```

### Examples for Kubernetes

```
kubectl run etcdcli --rm --tty -i --restart='Never' \
  --image luigidifraia/etcdcli:v1.0.0 \
  --env="ETCDCTL_API=3" \
  -- --endpoints=http://my-etcd.etcd.svc.cluster.local:2379 member list
```
