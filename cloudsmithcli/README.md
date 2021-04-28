# Docker image for the Cloudsmith CLI

## TL;DR

The examples below assume that you have exported your Cloudsmith API key into the environment variable CLOUDSMITH_API_KEY.

### List Helm packages in repo

```
docker run --rm \
  --env "CLOUDSMITH_API_KEY" \
  luigidifraia/cloudsmithcli:v1.0.0 \
  ls pkg YOUR-ACCOUNT/YOUR-REPO -q 'format:helm' -F json | jq .
```

### Tag package in repo

```
docker run --rm \
  --env "CLOUDSMITH_API_KEY" \
  luigidifraia/cloudsmithcli:v1.0.0 \
  tags add YOUR-ACCOUNT/YOUR-REPO/PACKAGE version:1.0.3
```
