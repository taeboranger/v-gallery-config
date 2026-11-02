# Retired media endpoint

The media endpoint is disabled. This overlay intentionally retains only the shared `letsencrypt-anyproject` ClusterIssuer, because active bangsell, sample and soop-talent certificates depend on it. Do not delete that issuer when retiring media.

The ingress and certificate YAML files are retained as inactive recovery references, not included in kustomization.yaml. MinIO data and database contents have not been deleted.
