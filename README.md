# declarest-bundle-rundeck

Rundeck metadata bundle for DeclaREST.

## Bundle manifest

This repository ships `bundle.yaml` as the canonical bundle manifest contract.

OpenAPI contract:

- `declarest.openapi` points to the bundled `openapi.yml`
- `sources` includes Rundeck API documentation

## Included metadata scope

This baseline bundle ships metadata for:

- `/projects/_` (Rundeck Project APIs)
- `/projects/_/jobs/_` (Rundeck Job APIs)
- `/projects/_/nodes/_` (Rundeck resource model source APIs)
- `/projects/_/secrets/_` (Rundeck key storage APIs)

## Release contract

Tag releases must follow `v<version>`. The workflow stamps that version into the release artifact's `bundle.yaml`; the committed repository copy stays on the placeholder release value.

Published archive naming contract:

- `rundeck-bundle-<version>.tar.gz`

Published archive contents:

- `bundle.yaml`
- `metadata/**`
- `declarest.openapi` target file (`openapi.yml`)

The release workflow validates:

- the stamped `bundle.yaml` version matches the release tag
- `distribution.artifactTemplate` matches `<name>-{version}.tar.gz`
- `declarest.metadataRoot` exists and contains metadata definitions
- `declarest.openapi` is a local file path that exists in the repository
