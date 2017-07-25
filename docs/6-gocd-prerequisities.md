# Prerequsities for integrating with Go.cd

The following workflow expects the following to be true:

1. The kubeconfig file to access the Kubernetes cluster to be present on the go.cd agent here: `~/.kube/config`

2. The go.cd agent has `build-essential`, `kubectl` and `helm` installed.

2. The Kubernetes cluster to have a dedicated ingress node.

3. The IP address of the dedicated ingress node to be known.

## Integrating with Go.cd

To integrate the repo with go.cd click [here](7-integrating-with-gocd.md)
