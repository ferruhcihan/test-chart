# Otomi quick start for creating workloads

The `otomi-quickstart-k8s-deployment` chart can be used to create a Kubernetes `Deployment`. Optionally a `HPA` and a `Service Monitor` can be created.

## About Otomi quick starts

The Developer Catalog is a library of curated Helm charts to create Kubernetes resources. By default the Developer catalog contains a set of Otomi provided templates to get started quickly. The Otomi provided templates can be used out-of-the-box, but can also be modified depending on your requirements or be removed from the catalog. The contents of the catalog are managed by the administrator of the platform. Team members only have read access to the repository that contains all the catalog Helm charts.

## How to use this quick start

1.  Create a Build and copy the image repository name of your build in the list of builds
2.  Go to the `values` tab en fill in a name for your workload
3.  Add the image repository name of your build to the `image.repository` parameter value
4.  Add the tag of your build to the `image.tag` parameter value
5.  Optional: Change other parameter values as needed

## Parameters

### Required parameters

| Name             | Description                              | Value |
|------------------|------------------------------------------|-------|
| image.repository | Image repository for the image to deploy | `""`  |
| image.tag | Image tag for the image to deploy               | `""`  |

### Otomi controlled parameters

| Name             | Description                                                                                                                       | Value |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------|-------|
| fullnameOverride | String to fully override deployment.fullname template. Used by Otomi to set the name for all resources based on the workload name | `""`  |

### Optional parameters

| Name             | Description                                                                                                                       | Value           |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------|-----------------|
| pullPolicy       | Image pull policy. Choose between `always`, `never` or (default) `IfNotPresent`                                                   | `IfNotPresent`  |
| env              | Environment variables for containers                                                                                              | `[]`            |
| podAnnotations   | Additional Annotations for pods                                                                                                   | `{}`            |
| podLabels        | Additional labels for pods                                                                                                        | `{}`            |
| commonLabels     | Additional labels for all resources                                                                                               | `{}`            |
| serviceAccount.annotations | Annotations for the service account                                                                                     | `{}`            |
| serviceAccount.imagePullSecrets | An array of imagePullSecrets. Only use when deploying images from external registries. When images are deployed from the local Harbor registry, pull secrets are already added to the service account. | `[]`            |