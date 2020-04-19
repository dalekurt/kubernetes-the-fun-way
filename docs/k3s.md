# How-to Install K3s

## Setup the Master
First thing to do is install the server. We will do this on master:

```bash
curl -sfL https://get.k3s.io | sh -
```

Check that the systemd service started correctly

```bash
sudo systemctl status k3s
```

Grab the join key from this node with:

```bash
sudo cat /var/lib/rancher/k3s/server/node-token
```

## Setup the other nodes
Now we can install the agents on each remaining node:

```
export MASTER=<MASTER_NODE_IP>
export TOKEN=<NODE_TOKEN>
curl -sfL https://get.k3s.io | K3S_URL=https://${MASTER}:6443 K3S_TOKEN=${TOKEN} sh -
```

## Connect to the Kubernetes cluster remotely

Get the KUBECONFIG from the Master

```bash
sudo cat /etc/rancher/k3s/k3s.yaml
```
