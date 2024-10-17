# Design Tool Manifest (NGLOTS)

Personnal kubernetes deployment manifests of [Penpot](https://github.com/penpot/penpot) design tool.

## GitOps

I'm using FluxCD to automate penpot deployment on my kubernetes cluster.

### Source

```shell
flux create source git nglots \
--url=https://github.com/noynto/nglots \
--branch=main \
--interval=1m
```

### Format

```shell
flux create kustomization nglots \
--target-namespace=nglots \
--source=nglots \
--prune=true
```
