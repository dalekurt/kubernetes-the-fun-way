Setup the Master
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

# Setup the nodes
Now we can install the agents on each remaining node:

```
curl -sfL https://get.k3s.io | K3S_URL=https://10.0.0.10:6443 K3S_TOKEN=K1064ea7a1329926380bbf6b74e7471362be221d9f88b548e712ca78af58145a35b::server:fe6efb1dcefc43df12b33fd3be81b486 sh -
```
