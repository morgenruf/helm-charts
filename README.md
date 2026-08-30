# Morgenruf Helm Charts

[![Chart](https://img.shields.io/badge/helm-charts.morgenruf.dev-0f1689)](https://charts.morgenruf.dev)
[![Release](https://img.shields.io/github/v/release/morgenruf/morgenruf?label=app&color=2ea043)](https://github.com/morgenruf/morgenruf/releases/latest)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Official Helm chart repository for [Morgenruf](https://morgenruf.dev) — self-hosted, open-source Slack standup bot.

## Add the repo

```bash
helm repo add morgenruf https://charts.morgenruf.dev
helm repo update
```

## Install (minimal — quickstart)

```bash
helm upgrade --install morgenruf morgenruf/morgenruf \
  --namespace morgenruf --create-namespace \
  --set slack.clientId="YOUR_CLIENT_ID" \
  --set slack.clientSecret="YOUR_CLIENT_SECRET" \
  --set slack.signingSecret="YOUR_SIGNING_SECRET" \
  --set externalDatabase.url="postgresql://user:pass@host:5432/morgenruf" \
  --set flaskSecretKey="$(openssl rand -hex 32)" \
  --set app.url="https://api.your-domain.com"
```

## Required values

| Parameter | Description |
|---|---|
| `slack.clientId` | Slack app Client ID (from Basic Information) |
| `slack.clientSecret` | Slack app Client Secret — 32 hex chars |
| `slack.signingSecret` | Slack Signing Secret — 32 hex chars (≠ clientSecret!) |
| `externalDatabase.url` | PostgreSQL URL: `postgresql://user:pass@host:5432/db` |
| `flaskSecretKey` | Random 32-byte hex: `openssl rand -hex 32` |
| `app.url` | Public HTTPS URL where the bot is reachable |

## Optional values

| Parameter | Default | Description |
|---|---|---|
| `resend.apiKey` | `""` | Resend API key for welcome & digest emails |
| `ingress.enabled` | `true` | Disable for Cloudflare Tunnel |
| `ingress.className` | `"nginx"` | Ingress class name |
| `postgresql.enabled` | `false` | Bundled PostgreSQL (testing only) |

## Available charts

| Chart | Version | Description |
|---|---|---|
| `morgenruf/morgenruf` | 0.3.0 | Self-hosted Slack standup bot |

## Links

- 🌐 [morgenruf.dev](https://morgenruf.dev)
- 📚 [docs.morgenruf.dev](https://docs.morgenruf.dev)
- 💻 [github.com/morgenruf/morgenruf](https://github.com/morgenruf/morgenruf)

---

<sub>Part of [Morgenruf](https://github.com/morgenruf/morgenruf), the self-hosted Slack standup bot &middot; [morgenruf.dev](https://morgenruf.dev) &middot; [docs](https://docs.morgenruf.dev) &middot; [status](https://status.morgenruf.dev)</sub>
