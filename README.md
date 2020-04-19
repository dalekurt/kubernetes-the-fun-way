![LO_Horizontal_Full Colour](https://user-images.githubusercontent.com/93077/73411035-fab53880-42d1-11ea-9542-e9b2af89f086.png)

# Kubernetes the fun way

## Table of contents

![Hardware](assets/raspberry-pi-cluster.JPG)

The last few years, I’ve had several thoughts about getting into hobbyist culture behind Raspberry Pi, but have no justification other than it being a fun project or for the share tinkering around. There has always been an interest in running a cluster, since I read about Raspberry Pi Cluster projects on blogs and watch several hours of YouTube videos, wishing I thought of that. Needless to say, this year (2019) would not pass me by without start a personal project. After an unplanned venture to TinkerSphere in New York City with a co-worker, I purchased my very first Raspberry Pi, which furthered my thoughts about building a cluster of Raspberry Pis to tinker with, so why not build a Kubernetes cluster.

## Why?

The initial inspiration for running Kubernetes on a Raspberry Pi cluster came from reading Kasper Nissen’s blog post on kubecloud.io, the second was to prepare myself for the Certified Kubernetes Administrator (CKA) exam later in the year. That said, I reached out to Kasper on Twitter for further details about the laser cut rack, and I reached out to Fabberz NYC to place an order using his template.

I learn when things don’t work.

## Target Audience
This tutorial is intended for person who are interested in learning Kubernetes and would like to understand the challenges of running Kubernetes on bare-metal hardware. As the tutorial is aim towards running Kubernetes on ARM, general knowledge will prove to be useful.
> Note This is not intended for a production environment

## Cluster Details
- [Raspbian](https://www.raspbian.org/)
- [K3s](https://k3s.io/)
- [Helm](https://helm.sh)
- [Prometheus]()
- [Rook](https://rook.io/)
- [FluxCD](https://fluxcd.io/)
- [Argo Tunnel](https://github.com/cloudflare/cloudflare-ingress-controller)



# My Network Topology

| IP | Description |
| --- | --- |
| 10.0.0.1 | Gateway (Ubiquiti EdgeRouter X) |
| 10.0.0.10 | k3s master (master) |
| 10.0.0.11 | k3s node (node-01) |
| 10.0.0.12 | k3s node (node-02) |
| 10.0.0.13 | k3s node (node-03) |

