# OpenApi Versioning

* The version is specified in the format `MAJOR.MINOR.PATCH`, where `MAJOR`, `MINOR`, and `PATCH` are unsigned integer values.
* The `MAJOR` version number **must** be aligned with the major releases of service and must represent a finalized set of `api/v{MAJOR}` endpoints. After a `MAJOR` version is released, no new endpoints with the same version prefix `v{MAJOR}` may be added.
* The `MINOR` version number **must** be incremented if:
  * backward-compatible or incompatible OpenAPI changes are made
  * a new endpoint is added
* The `PATCH` version number **must** be incremented if any minor cleanup is done, e.g., updates to the `title`, `description`, or `example` fields.


## Referencing to the existing OpenApi spec file

*Any* reference to an existing OpenAPI specification file
**must** be a reference the specified [realease](./release_policy.md) using the following format:
`<app_name>-openapi/vMAJOR.MINOR.PATCH`.

The release version **must** match the specified version of the OpenAPI specification file.