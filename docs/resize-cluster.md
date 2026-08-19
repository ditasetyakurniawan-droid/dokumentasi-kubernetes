# Kubernetes Resize Guide

## Prinsip
Resize cluster dilakukan berdasarkan kebutuhan workload, CPU, memory, dan kapasitas node.

## Sebelum Resize

1. Cek kondisi cluster.
2. Pastikan seluruh node Ready.
3. Backup konfigurasi penting.

## Monitoring

```bash
kubectl top nodes
kubectl top pods -A
```

## Scaling Workload

Gunakan resource request dan limit yang sesuai sebelum melakukan scaling.

Contoh:

```bash
kubectl scale deployment <nama-deployment> --replicas=<jumlah>
```

## Validasi Setelah Perubahan

```bash
kubectl get pods -A
kubectl get nodes
```

Pastikan tidak ada pod crash atau node NotReady.
