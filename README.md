# Morgenruf Helm Charts

Official Helm chart repository for [Morgenruf](https://morgenruf.dev) — open-source Slack standup bot.

## Usage

### Option 1 — Traditional Helm repo (recommended)

```bash
helm repo add morgenruf https://charts.morgenruf.dev
helm repo update
helm install morgenruf morgenruf/morgenruf \
  --namespace morgenruf \
  --create-namespace \
  --set slack.clientId="YOUR_CLIENT_ID" \
  --set slack.clientSecret="YOUR_CLIENT_SECRET" \
  --set slack.signingSecret="YOUR_SIGNING_SECRET" \
  --set postgresql.enabled=true
```

### Option 2 — OCI (Helm 3.8+)

```bash
helm install morgenruf \
  oci://ghcr.io/morgenruf/charts/morgenruf \
  --namespace morgenruf \
  --create-namespace \
  --set slack.clientId="YOUR_CLIENT_ID" \
  --set slack.clientSecret="YOUR_CLIENT_SECRET" \
  --set slack.signingSecret="YOUR_SIGNING_SECRET"
```

## Configuration

| Parameter | Description | Default |
|-----------|-------------|---------|
| `slack.clientId` | Slack OAuth Client ID | `""` |
| `slack.clientSecret` | Slack OAuth Client Secret | `""` |
| `slack.signingSecret` | Slack Signing Secret | `""` |
| `postgresql.enabled` | Deploy bundled PostgreSQL | `true` |
| `externalDatabase.url` | External PostgreSQL URL | `""` |
| `app.url` | Public bot URL | `https://api.morgenruf.dev` |
| `resend.apiKey` | Resend API key for emails | `""` |

## Links

- 🌐 [morgenruf.dev](https://morgenruf.dev)
- 📚 [docs.morgenruf.dev/helm](https://docs.morgenruf.dev/helm)
- 💻 [github.com/morgenruf/morgenruf](https://github.com/morgenruf/morgenruf)
