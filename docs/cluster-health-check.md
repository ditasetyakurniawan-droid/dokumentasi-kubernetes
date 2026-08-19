# Kubernetes Cluster Health Check Runbook

## Tujuan
Dokumen ini menjadi panduan pemeriksaan kesehatan cluster Kubernetes.

## Pemeriksaan Node

```bash
kubectl get nodes
```

Pastikan seluruh node memiliki status Ready.

## Pemeriksaan Resource

```bash
kubectl top nodes
kubectl top pods -A
```

Gunakan data CPU dan memory untuk menentukan kebutuhan scaling.

## Pemeriksaan Pod Bermasalah

```bash
kubectl get pods -A --field-selector=status.phase!=Running,status.phase!=Succeeded
```

## Pemeriksaan Dasar Cluster

```bash
kubectl get namespaces
kubectl get deployments -A
kubectl get services -A
```

## Prinsip Operasional

- Dokumentasikan setiap perubahan cluster.
- Gunakan branch dan pull request untuk perubahan konfigurasi.
- Jangan menyimpan secret di repository.
