# k8s-cloud-builder

This config builds the Docker container image used to perform kubernetes releases and push it to GCR. 
The Docker container image should be updated every time a dependency is updated.

To update run:
```
gcloud container builds submit --config cloudbuild.yaml .
```

## Dependencies

Packages installed on the build container are documented here.

This image is extending the official Google Cloud Builder Docker image.

- **curl** - Used for fetching build dependencies as part of the container
  build.
- **wget** - Used for fetching dependencies as part of the Istio build.
- **gnupg2** - Used for adding public keys for apt repositories.

- **git** - Used to fetch source code from Git repositories.
- **openjdk-8-jdk** - Required by Bazel.
- **python** - Required by Istio build and various dependencies.
- **Google Cloud SDK** - Used to release artifacts into Google Cloud Storage.
