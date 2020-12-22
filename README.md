# kube-manifest-examples
Collection of example kubernetes manifests

# Known Issues

`kubectl` caches the api-resources the api tells it about each time you run a command. This means if you run `kustomize build common | kubectl apply -f -` it will fail with a confusing:

```
unable to recognize "STDIN": no matches for kind "Application" in version "argoproj.io/v1alpha1"
```

Even though earlier in the apply that CRD was successfully created.

This means you have to run `kustomize build common | kubectl apply -f -` twice to get everything created/applied

## Issues for reference

- https://github.com/kubernetes-sigs/kustomize/issues/1510
- https://github.com/kubernetes-sigs/kustomize/issues/1510#issuecomment-529537309
- https://github.com/kubernetes-sigs/kustomize/issues/3074
