# openclaw-image-mirror

Mirrors `ghcr.io/openclaw/openclaw` tags to `docker.io/openclaw/openclaw` using GitHub Actions + `skopeo copy --all` (preserves multi-arch manifests).

## Required GitHub Actions secrets

- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`

Optional (only if GHCR requires auth):
- `GHCR_USERNAME`
- `GHCR_TOKEN`

## How it works

- Runs on a schedule (every 30 minutes) and can be run manually via **workflow_dispatch**.
- Lists tags on GHCR and Docker Hub.
- Copies only missing tags.
