# Deployment - secrets-navigator

**Use case:** Regulated Product Teams use the service to quarantine risky artifacts across signed container releases, so secret exposure windows close automatically.

## Infra requirements
→ `terraform/INFRA_REQUIREMENTS.md` - CPU/RAM/storage/network/cost breakdown

## GitOps
Flux watches `main` and reconciles changes automatically.

## Rollback
```
./scripts/rollback.sh
kubectl rollout undo deploy/secrets-navigator -n secrets-navigator
```
Usually < 30 sec.

## Cost
Render - $0/mo

The focus is supply-chain hardening: SBOMs, Cosign signatures, and policy enforcement across build and deploy.
