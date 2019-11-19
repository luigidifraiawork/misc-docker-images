# Docker image for the AWS CLI

## TL;DR

### Examples for Docker

#### List bucket contents

```
docker run --rm \
  --env "AWS_ACCESS_KEY_ID=AKIAIOSFODNN7INVALID" \
  --env "AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYINVALIDKEY" \
  --env "AWS_REGION=eu-west-2" \
  luigidifraia/awscli:v1.0.2 \
  s3 ls s3://cs-odc-data
```

Or:

```
docker run --rm \
  --env-file=$HOME/.aws_env.list \
  luigidifraia/awscli:v1.0.2 \
  s3 ls s3://cs-odc-data
```

With `$HOME/.aws_env.list` having the following contents:

```
AWS_ACCESS_KEY_ID=AKIAIOSFODNN7INVALID
AWS_SECRET_ACCESS_KEY=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
AWS_REGION=eu-west-2
```

#### Copy a local file to a bucket

```
docker run --rm \
  --env-file=$HOME/.aws_env.list \
  --volume /home/luigidifraia/cs-odc-data-s3-explorer:/tmp/cs-odc-data-s3-explorer luigidifraia/awscli:v1.0.2 \
  s3 cp /tmp/cs-odc-data-s3-explorer/index.html s3://cs-odc-data
```

### Examples for Kubernetes

#### List bucket contents

```
kubectl run awscli --rm --tty -i --restart='Never' \
  --image luigidifraia/awscli:v1.0.2 \
  --env="AWS_ACCESS_KEY_ID=AKIAIOSFODNN7INVALID" \
  --env="AWS_SECRET_ACCESS_KEY=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" \
  --env="AWS_REGION=eu-west-2" \
  -- s3 ls s3://cs-odc-data
```
