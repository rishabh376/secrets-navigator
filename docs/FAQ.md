# FAQ - secrets-navigator

**Q: What problem does this actually solve?**
A: Regulated Product Teams use the service to quarantine risky artifacts across signed container releases, so secret exposure windows close automatically.

Pain point: Secret rotation depends on calendar reminders and late-night manual checks.

**Q: Free to run?**
A: Yep. Render - $0/mo. See `terraform/INFRA_REQUIREMENTS.md`

**Q: Production ready?**
A: Yes - SLOs, security hardening, DR runbook, Helm, Terraform, monitoring.

**Q: Stack?**
A: Go, Kyverno, Vault, Falco, Sigstore, In-Toto, SLSA L3

**Q: What infra do I need?**
A: `terraform/INFRA_REQUIREMENTS.md` has the full breakdown - CPU/RAM/storage/network/cost.
