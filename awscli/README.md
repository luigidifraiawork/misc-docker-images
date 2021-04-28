# Docker image for the AWS CLI

## TL;DR

Some of the examples below assume that you have exported your AWS credentials for command line access into the environment variables AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, and AWS_REGION.
Depending on your account type you might also have to export a session token into the environment variable AWS_SESSION_TOKEN.

### Examples for Docker

#### List bucket contents

```
docker run --rm \
  --env "AWS_ACCESS_KEY_ID" \
  --env "AWS_SECRET_ACCESS_KEY" \
  --env "AWS_REGION" \
  luigidifraia/awscli:v1.0.4 \
  s3 ls s3://my-bucket
```

Or:

```
docker run --rm \
  --env-file=$HOME/.aws_env.list \
  luigidifraia/awscli:v1.0.4 \
  s3 ls s3://my-bucket
```

With `$HOME/.aws_env.list` having contents similar to:

```
AWS_ACCESS_KEY_ID=AKIAIOSFODNN7INVALID
AWS_SECRET_ACCESS_KEY=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
AWS_REGION=eu-west-2
```

#### Copy a local file to a remote S3 bucket

```
docker run --rm \
  --env-file=$HOME/.aws_env.list \
  --volume /home/luigidifraia/my-bucket-s3-explorer:/tmp/my-bucket-s3-explorer luigidifraia/awscli:v1.0.4 \
  s3 cp /tmp/my-bucket-s3-explorer/index.html s3://my-bucket
```

### Examples for Kubernetes

#### List bucket contents

```
kubectl run awscli --rm --tty -i --restart='Never' \
  --image luigidifraia/awscli:v1.0.4 \
  --env="AWS_ACCESS_KEY_ID" \
  --env="AWS_SECRET_ACCESS_KEY" \
  --env="AWS_REGION" \
  -- s3 ls s3://my-bucket
```
