# kubectl Cheatsheet

## Setup

```bash
# Aliases — add to ~/.bashrc or ~/.zshrc
alias k=kubectl
export do="--dry-run=client -o yaml"
export now="--force --grace-period 0"

# Context
kubectl config get-contexts
kubectl config use-context <name>
kubectl config current-context

# Kubeconfig
export KUBECONFIG=~/.kube/config
```

## Pods

```bash
# List
k get pods -A                          # all namespaces
k get pods -n <ns> -o wide             # with node info
k get pods --field-selector=status.phase=Running

# Describe / logs
k describe pod <pod> -n <ns>
k logs <pod> -n <ns> -c <container>
k logs <pod> -n <ns> --previous        # crashed container
k logs -f <pod> -n <ns>               # follow

# Exec
k exec -it <pod> -n <ns> -- bash
k exec -it <pod> -n <ns> -c <container> -- sh

# Create quickly
k run nginx --image=nginx:alpine $do > pod.yaml
k run tmp --image=busybox --rm -it --restart=Never -- sh   # debug pod

# Delete fast
k delete pod <pod> $now
```

## Deployments

```bash
k get deploy -n <ns>
k describe deploy <name> -n <ns>
k rollout status deploy/<name> -n <ns>
k rollout history deploy/<name> -n <ns>
k rollout undo deploy/<name> -n <ns>
k scale deploy <name> --replicas=3 -n <ns>

# Create
k create deploy nginx --image=nginx:alpine $do > deploy.yaml
```

## Services

```bash
k get svc -A
k expose deploy <name> --port=80 --target-port=8080 $do > svc.yaml
k port-forward svc/<name> 8080:80 -n <ns>
```

## ConfigMaps & Secrets

```bash
k create configmap <name> --from-literal=key=value $do
k create configmap <name> --from-file=config.yaml $do
k create secret generic <name> --from-literal=password=secret $do
k get secret <name> -o jsonpath='{.data.password}' | base64 -d
```

## Namespaces

```bash
k get ns
k create ns <name>
k delete ns <name>
```

## RBAC

```bash
k get clusterroles
k get clusterrolebindings
k get roles -n <ns>
k get rolebindings -n <ns>
k auth can-i create pods --as=<user> -n <ns>

# Create
k create role <name> --verb=get,list --resource=pods $do
k create rolebinding <name> --role=<role> --user=<user> -n <ns> $do
k create clusterrolebinding <name> --clusterrole=<role> --serviceaccount=<ns>:<sa> $do
```

## Nodes

```bash
k get nodes -o wide
k describe node <name>
k cordon <node>        # prevent scheduling
k uncordon <node>
k drain <node> --ignore-daemonsets --delete-emptydir-data
```

## Troubleshooting

```bash
# Pod stuck in Pending
k describe pod <pod> -n <ns>   # check Events section

# Pod CrashLoopBackOff
k logs <pod> --previous -n <ns>

# Check resource usage
k top pods -n <ns>
k top nodes

# Events (last 30 min)
k get events -n <ns> --sort-by='.lastTimestamp'

# Network debug
k run netdebug --image=nicolaka/netshoot --rm -it --restart=Never -- bash
```

## etcd (CKA)

```bash
# Backup
ETCDCTL_API=3 etcdctl snapshot save /backup/etcd.db \
  --endpoints=https://127.0.0.1:2379 \
  --cacert=/etc/kubernetes/pki/etcd/ca.crt \
  --cert=/etc/kubernetes/pki/etcd/server.crt \
  --key=/etc/kubernetes/pki/etcd/server.key

# Restore
ETCDCTL_API=3 etcdctl snapshot restore /backup/etcd.db \
  --data-dir=/var/lib/etcd-restore
```

## Certificates (CKA)

```bash
# Check cert expiry
kubeadm certs check-expiration

# Renew all
kubeadm certs renew all
```

---
*Last updated: 2026-06 | Stack: EKS 1.35 arm64*
