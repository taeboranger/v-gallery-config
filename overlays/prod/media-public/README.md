# media.anyproject.dev

Argo CD application: `media-anyproject` (`../../../../argocd-media-anyproject.yaml`).
This overlay exposes the existing `default/minio-external:9000` service through ingress-nginx.
Only `media.anyproject.dev` is supported. The legacy cagea1.com DNS/Tunnel route has been retired. The older `minio-public` overlay is intentionally empty and must not recreate the retired public endpoint. Any manually managed legacy Ingress is not owned by this application.

TLS uses the shared `letsencrypt-anyproject` ClusterIssuer. Its existing API token must be supplied as `cert-manager/cloudflare-api-token-anyproject` with key `api-token`; never commit the token. This issuer only handles `anyproject.dev`.
Cloudflare DNS and the `homeserver-web` published route must map this hostname to the existing tunnel.
