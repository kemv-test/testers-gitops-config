# TESTERS

## Usage

To initialize your first Argo CD application run:


```
mkdir dev/hello-world
echo 'apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: hello-world
  namespace: argo-cd
spec:
  destination:
    namespace: hello-world
    server: https://kubernetes.default.svc
  project: default
  source:
    repoURL: https://tv2.jfrog.io/artifactory/ccs-helm-release
    targetRevision: 1.1.0
    chart: generic-service
    helm:
      values: |
        image:
          registry: example.com
          repository: foobar
          tag: 1.2.3
  syncPolicy:
    automated:
      prune: true
      selfHeal: true' > dev/hello-world/hello-world.yaml

## environments

```
.
├── README.md.tftpl
├── dev
├── prod
└── stage
```

