# Deploying the application to Kubernetes

## IMPORTANT

The following workflow expects the following to be true:

1. The kubeconfig file to access the Kubernetes cluster to be present here: `~/.kube/config`

2. The Kubernetes cluster to have a dedicated ingress node.

3. The IP address of the dedicated ingress node to be known.

## Deployment

To deploy the application simple execute the following command:

```
$ make deploy-dev
```

Under the covers this performs the following actions:

1. Packages the helm chart (java-demo-app) to be the same version as the docker image

2. Deploys the helm package to the Kubernetes cluster using the default `values.yaml` file.

## Verification

Firstly we need to add the following to `/etc/hosts`

```
<ingress ip address> java-demo-app.example.com
```

Now browse to: <a href="http://java-demo-app.example.com/greeting">http://java-demo-app.example.com/greeting</a> you should be greeted with:

```
{"id":1,"content":"Hello, World!"}
```