# Kubernetes Disaster Recovery Notes

## Backup

Backup yang perlu diperhatikan:

- Kubernetes manifests
- Persistent Volume data
- etcd database (untuk cluster self-managed)

## Recovery Checklist

1. Validasi node control plane.
2. Restore data sesuai prosedur.
3. Validasi API server.
4. Validasi workload.

## Validasi

```bash
kubectl get nodes
kubectl get pods -A
```
