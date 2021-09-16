# Docker image for parquet-tools (Python)

## TL;DR

### Example for Docker

```
docker run --rm \
  -v $(pwd):/tmp:ro \
  luigidifraia/parquet-tools:v1.0.0 \
  csv "/tmp/*.parquet"
```
