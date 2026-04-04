# Morgenruf Helm Charts

Official Helm charts for [Morgenruf](https://morgenruf.dev) — hosted at `charts.morgenruf.dev`.

## Usage

```bash
# OCI (recommended)
helm upgrade --install morgenruf \
  oci://ghcr.io/morgenruf/helm/morgenruf \
  --namespace morgenruf --create-namespace \
  --set secret.slackBotToken="xoxb-..." \
  --set secret.slackSigningSecret="..."

# Classic Helm repo
helm repo add morgenruf https://charts.morgenruf.dev
helm repo update
helm install morgenruf morgenruf/morgenruf
```

## Charts

| Chart | Description | Version |
|-------|-------------|---------|
| [morgenruf](./charts/morgenruf) | Self-hosted Slack standup bot | ![version](https://img.shields.io/github/v/release/morgenruf/morgenruf) |
