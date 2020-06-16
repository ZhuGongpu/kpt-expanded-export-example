# kpt-expanded-export-example

This repo demostrates the _working-in-progress_ `kpt fn export --expand` command.

`functions.yaml` contains three functions from [Kpt Functions Catalog](https://googlecontainertools.github.io/kpt-functions-catalog/):

- [inject-tshirt-sizes](https://github.com/kubernetes-sigs/kustomize/tree/master/functions/examples/injection-tshirt-sizes): Sets CPU and memory reservations on all containers for Resources annotated with tshirt size.
- [label-namespace](https://github.com/GoogleContainerTools/kpt-functions-sdk/blob/master/ts/hello-world/src/label_namespace.ts): Adds a label to all Namespaces.
- [validate-rolebinding](https://github.com/GoogleContainerTools/kpt-functions-sdk/blob/master/ts/demo-functions/src/validate_rolebinding.ts): Blocks a list of subjects in RoleBinding objects.

The [GitHub workflow](./.github/workflows/main.yaml) contains these steps:

1. Checkout the latest code from the master branch of this repo.
2. Run all the kpt functions above one by one per step.
   - These steps are generated by the `kpt fn export --expand` command.
3. Commit all changes and push into the [`hydrate`](https://github.com/ZhuGongpu/kpt-expanded-export-example/tree/hydrate) branch that is ready to be applied into a Kubernetes cluster.
