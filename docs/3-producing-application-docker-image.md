# Producing the application docker image

Now we have the application artefact we need to bundle this into a docker container.

Please execute the following command to perform this task:

```
$ make build-image
```

## Verification

### 1. Check docker images

If this was successful we can execute the following command:

```
$ docker images
```

The output should show the following:

```
REPOSITORY                       TAG                 IMAGE ID            CREATED             SIZE
quay.io/apprenda/java-demo-app   1.1.1               19c01519d798        7 seconds ago       95.6MB
```

### 2. Check labels on the docker image

Additionally we can check the labels of the image by executing the following command:

```
$ docker inspect quay.io/apprenda/java-demo-app:1.1.1
```

The output should contain the following:

```
"Labels": {
    "build.dockerfile": "/Dockerfile",
    "build.on": "2017-07-25T15:17:57Z",
    "git.branch": "master",
    "git.commit": "9f6da8a4c6443561ce19e5d09a608303837b9d33",
    "git.repository": "https://github.com/apprenda/sample-dockerised-java-app"
}
```

### 3. Run the application container locally

Execute the following command:

```
docker run -d -p 8080:8080 quay.io/apprenda/java-demo-app:1.1.1
```

Now browse to: <a href="http://localhost:8080/greeting">http://localhost:8080/greeting</a> you should be greeted with:

```
{"id":1,"content":"Hello, World!"}
```

## Uploading the docker image to the container registry

To upload the docker image to our container registry click [here](4-uploading-docker-image-to-registry.md)