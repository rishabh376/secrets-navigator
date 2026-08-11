# Operations Runbook - secrets-navigator

Regulated Product Teams use the service to quarantine risky artifacts across signed container releases, so secret exposure windows close automatically.

**On-call? Read this first.**

## Deploy
```
kubectl apply -k k8s/ -n secrets-navigator
kubectl rollout status deploy/secrets-navigator -n secrets-navigator
```

## Rollback (when things go red)
```
./scripts/rollback.sh
# usually < 30sec
```

## Scale up NOW
```
kubectl scale deploy/secrets-navigator --replicas=10 -n secrets-navigator
```

## Logs
```
kubectl logs -l app=secrets-navigator -n secrets-navigator -f --tail=200
```

## Crashloop?
```
kubectl describe pod -l app=secrets-navigator -n secrets-navigator
kubectl logs <pod> --previous -n secrets-navigator
```
90% of the time: missing env var in ConfigMap.

## Metrics
`curl localhost:8080/metrics` or Grafana dashboard in `monitoring/`

## DR / Failover
See `docs/DISASTER_RECOVERY.md` - RTO 15m

We actually tested this. 11 min.
