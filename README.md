# CRDs-catalog

Built from https://github.com/datreeio/CRDs-catalog, based on the CRDs we use.

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

Ensure you're **connected to a non-production cluster** then run `task crd-extract` to update the CRD files.
