# Setup - secrets-navigator

Regulated Product Teams use the service to quarantine risky artifacts across signed container releases, so secret exposure windows close automatically.

1. **Infra first**: `cd terraform && terraform init && terraform apply`
2. `kubectl apply -k k8s/ -n secrets-navigator`
3. `kubectl port-forward svc/secrets-navigator 8080:80 -n secrets-navigator`
4. `curl localhost:8080/healthz`

Env vars: `PORT=8080`, `LOG_LEVEL=info`

Runtime detection and telemetry let us prove the security controls are actually working in prod.
