# Uploading the docker image to the container registry

Firstly we need to make sure we specify the [Quay.io](https://quay.io/repository/) password.

To do this execute the following command:

```
$ export QUAY_PASSWORD=<password>
```

To upload the image to [Quay.io](https://quay.io/repository/) execute the following command:

```
$ make push
```

Under the covers the command above executes the following steps:

- Logs the docker daemon into quay.io to allow for uploading
- Uploads the image we built to quay.io repository specificed in the Makefile.
- Logs the docker daemon out of accessing quay.io

## Deploying the application to Kubernetes

To deploy the application to Kubernetes click [here](5-deploying-the-application-to-kubernetes.md)