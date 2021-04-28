# Docker image for etcdctl

## TL;DR

### Examples for Docker

```
docker run --rm \
  --env "ETCDCTL_API=3" \
  luigidifraia/etcdctl:v1.0.4 \
  --endpoints=http://10.21.12.20:2379 member list
```

Or:

```
docker run --rm \
  --env-file=$HOME/.etcd_env.list \
  luigidifraia/etcdctl:v1.0.4 \
  --endpoints=http://10.21.12.20:2379 member list
```

With `$HOME/.etcd_env.list` having the following contents:

```
ETCDCTL_API=3
```

### Examples for Kubernetes

```
kubectl run etcdctl --rm --tty -i --restart='Never' \
  --image luigidifraia/etcdctl:v1.0.4 \
  --env="ETCDCTL_API=3" \
  -- --endpoints=http://my-etcd.etcd.svc.cluster.local:2379 member list
```
