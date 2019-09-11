# Docker image for the AWS CLI

## TL;DR

### Examples for Docker

```
docker run --rm \
  --env "AWS_ACCESS_KEY_ID=AKIAIOSFODNN7INVALID" \
  --env "AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYINVALIDKEY" \
  --env "AWS_REGION=eu-west-2" \
  luigidifraia/awscli:v1.0.0 \
  s3 ls s3://public-eo-data
```

Or:

```
docker run --rm \
  --env-file=$HOME/.aws_env.list \
  luigidifraia/awscli:v1.0.0 \
  s3 ls s3://public-eo-data
```

With `$HOME/.aws_env.list` having the following contents:

```
AWS_ACCESS_KEY_ID=AKIAIOSFODNN7INVALID
AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYINVALIDKEY
AWS_REGION=eu-west-2
```

### Examples for Kubernetes

```
kubectl run awscli --rm --tty -i --restart='Never' \
  --image luigidifraia/awscli:v1.0.0 \
  --env="AWS_ACCESS_KEY_ID=AKIAIOSFODNN7INVALID" \
  --env="AWS_SECRET_ACCESS_KEY=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" \
  --env="AWS_REGION=eu-west-2" \
  -- s3 ls s3://public-eo-data
```

### Output

```
                           PRE fiji/
                           PRE hosted/
                           PRE yemen/
2019-07-15 09:57:43       5458 index.html
```
