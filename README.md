# CRDs-catalog

Built from https://github.com/datreeio/CRDs-catalog, based on the CRDs we use.

We came up with this project due to validation errors we faced by using karpenter NodePool CRDs from the original one.
Extracting it from our dev cluster using the script provided by them, we were able to validate the CRDs using kubeconform.
The idea is this way we can keep a fresh list from this repo but still default to the original project for other CRDs.

## Usage

Different from the original project, we intend to use the here defined CRDs with kubeconform only.

### Kubeconform

```
kubeconform -schema-location default -schema-location 'https://raw.githubusercontent.com/TradrApi/CRDs-catalog/main/{{.Group}}/{{.ResourceKind}}_{{.ResourceAPIVersion}}.json' [MANIFEST]
```

## Contributing

Requirements:
- [python3](https://www.python.org/downloads/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl)
- [tasks](https://taskfile.dev/)
- [pre-commit](https://pre-commit.com/#install)

Run `task init` to bootstrap the project.

### Updating the CRDs

Ensure you're **connected to a non-production cluster** then run `task crd-extract` to update the CRD files.

### ⚠️ For MacOS users

To correctly extract the CRDs, you need to install `bash` using `brew install bash`.
Since Mac's default won't allow declaring associative arrays with `declare -A`.
