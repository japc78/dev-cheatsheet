# Kubernetes

## Commands

```bash

```

## K3S on Ubuntu

Prepare server with Ubuntu

### Install k3s

- <https://k3s.io/>
- <https://docs.k3s.io/quick-start>

```bash
# Install script
curl -sfL https://get.k3s.io | sh - 
# Check for Ready node, takes ~30 seconds 
k3s kubectl get node
```

## Install Helm Chart

- <https://helm.sh/docs/intro/install/>

```bash
curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null

sudo apt-get install apt-transport-https --yes

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list

sudo apt-get update
sudo apt-get install helm
```

Issues

### Error: Kubernetes cluster unreachable with helm 3.0

- https://github.com/k3s-io/k3s/issues/1126

```bash
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
```

## K9s Monitoring

- https://github.com/derailed/k9s
- https://webinstall.dev/k9s/

```bash
curl -sS https://webi.sh/k9s | sh
```
