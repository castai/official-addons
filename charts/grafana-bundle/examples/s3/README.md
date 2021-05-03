### Update AWS s3 storage

This guide will show how to setup s3 object storage to store loki chunks and index.

1. Create AWS IAM user for programmatic access.
2. Create storage bucket without public access.
3. Add bucket policy permissions from policy.json
   * Replace MY_ARN with created user's arn, eg: `arn:aws:iam::028075177508:user/am-aws-loki`
   * Replace MY_BUCKET with storage bucket name, eg: `aws-loki` 
4. Update helm chart with new values chart.
   * Replace MY_BUCKET_NAME, MY_REGION, MY_ACCESS_KEY_ID, MY_SECRET_KEY with your values.

```sh
helm upgrade grafana-bundle castai/grafana-bundle \
  -n grafana-bundle \
  -f loki-s3.yaml \
  --set "loki.config.storage_config.aws.bucketnames=MY_BUCKET_NAME" \
  --set "loki.config.storage_config.aws.region=MY_REGION" \
  --set "loki.config.storage_config.aws.access_key_id=MY_ACCESS_KEY_ID" \
  --set "loki.config.storage_config.aws.secret_access_key=MY_SECRET_KEY"
```
