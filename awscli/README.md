# Docker image for the AWS CLI

## TL;DR

Example for Kubernetes:

```
kubectl run awscli --rm --tty -i --restart='Never' \
  --image luigidifraia/awscli:v1.0.0 \
  --env="AWS_ACCESS_KEY_ID=AKIAIOSFODNN7INVALID" \
  --env="AWS_SECRET_ACCESS_KEY=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" \
  --env="AWS_REGION=eu-west-2" \
  -- aws s3 ls s3://public-eo-data
```

Output:

```
                           PRE fiji/
                           PRE hosted/
                           PRE yemen/
2019-07-15 09:57:43       5458 index.html
pod "awscli" deleted
```
