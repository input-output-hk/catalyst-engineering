<!-- cspell: OpenApi -->

# OpenApi Versioning

* The version is specified in the format `MAJOR.MINOR.PATCH`, where `MAJOR`, `MINOR`, and `PATCH` are unsigned integer values.
* An OpenApi schema spec considered **stable** if the `MAJOR` version number is **odd**, e.g. `1.*.*`, `3.*.*` etc.
* An OpenApi schema spec considered **unstable** if the `MAJOR` version number is **even**, e.g. `0.*.*`, `2.*.*` etc..
* The `MINOR` version number **must** be incremented if:
  * backward-compatible or incompatible OpenAPI changes are made
  * a new endpoint is added
* The `PATCH` version number **must** be incremented if any minor cleanup is done, e.g., updates to the `title`, `description`, or `example` fields.


## Referencing to the existing OpenApi spec file

*Any* reference to an existing OpenAPI specification file
**must** be a reference the specified [release](./release_policy.md) using the following format:
`<app_name>-openapi/vMAJOR.MINOR.PATCH`.

The release version **must** match the specified version of the OpenAPI specification file.

OpenApi schema specification file **must** been attached to a release.