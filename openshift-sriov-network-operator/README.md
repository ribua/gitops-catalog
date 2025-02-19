# OpenShift Single Root I/O Virtualization Operator

Installs the Openshift SR-IOV Operator.

Do not use the `base` directory directly, as you will need to patch the `channel` based on the version of OpenShift you are using, or the version of the operator you want to use.

The current *overlays* available are for the following channels:
* [4.9](overlays/4.9)
* [4.10](overlays/4.10)
* [4.11](overlays/4.11)

## Usage

If you have cloned the `gitops-catalog` repository, you can install the SR-IOV operator based on the overlay of your choice by running from the root `vse-catalog` directory

```
oc apply -k gitops-catalog/openshift-sriov-network-operator/overlays/<channel>
```

Or, without cloning:

```
oc apply -k https://github.com/redhat-cop/gitops-catalog/openshift-sriov-network-operator/overlays/<channel>
```

As part of a different overlay in your own GitOps repo:

```
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization
resources:
  - github.com/redhat-cop/gitops-catalog/openshift-sriov-network-operator/overlays/<channel>?ref=main
```
