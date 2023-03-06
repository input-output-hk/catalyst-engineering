# Release Policy

1. Create a new git tag for each release. Tags should follow a consistent naming convention, such as "vX.Y.Z" (where X, Y, and Z represent the major, minor, and patch versions of the release).

2. Publish release notes or changelog documenting the changes included in each release. It should be clear what new features have been added, what bugs have been fixed, and any breaking changes that may affect users.

3. Use [semantic versioning](https://semver.org/) to help users understand the scope of changes in each release. Semantic versioning involves incrementing the major version number for any release that includes breaking changes, the minor version number for new features, and the patch version number for bug fixes.

4. Use tags to mark stable releases that are suitable for production use. Development or pre-release versions should be labeled with appropriate tags, such as `alpha` or `beta`, to indicate their status.

Example:

```sh
1.1.0
1.1.0-rc.1
1.1.0-rc.1-alpha
1.1.0-rc.1-beta
1.1.0.dev.22+8eaec5d3
1.1.0.staging.23+8eaec5d3
```

5. Avoid modifying tags once they have been created. If a mistake is made, create a new tag with the corrected name or version number and document the change in the release notes.

6. Consider using signed tags to provide additional verification of the authenticity of each release. This can help users trust that they are downloading legitimate code.