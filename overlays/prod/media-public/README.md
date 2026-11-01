# media.anyproject.dev

Argo CD application: `media-anyproject` (`../../../../argocd-media-anyproject.yaml`).
This overlay exposes the existing `default/minio-external:9000` service through ingress-nginx.
The legacy `media.cagea1.com` ingress is unchanged. The older `minio-public` example is not used by this application.

TLS uses the shared `letsencrypt-anyproject` ClusterIssuer. Its existing API token must be supplied as `cert-manager/cloudflare-api-token-anyproject` with key `api-token`; never commit the token. This issuer only handles `anyproject.dev`.
Cloudflare DNS and the `homeserver-web` published route must map this hostname to the existing tunnel.
