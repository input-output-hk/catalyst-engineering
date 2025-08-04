# Release Policy

1. Each service, crate, library must be individually tagged

2. Create a new git tag for each release. Tags should follow a consistent naming convention, 
   such as `project/vx.x.x` where project is the value of `project.name` in the `blueprint.cue`. 

3. Publish release notes or changelog documenting the changes included in each release.
It should be clear what new features have been added, what bugs have been fixed,
and any breaking changes that may affect users.

4. Use [semantic versioning](https://semver.org/) to help users understand the scope of changes in each release.
Semantic versioning involves incrementing the major version number for any release that includes breaking changes,
the minor version number for new features, and the patch version number for bug fixes.

5. Use tags to mark stable releases that are suitable for production use.
Development or pre-release versions should be labeled with appropriate tags, such as `alpha` or `beta`, to indicate their status.

Example:

```txt
gateway/v0.1.0
gateway/v0.1.0-rc.1
gateway/v0.1.0-rc.1-alpha
gateway/v0.1.0-rc.1-beta
gateway/v0.1.0-dev.22+8eaec5d3
gateway/v0.1.0-staging.23+8eaec5d3
```

6. Avoid modifying tags once they have been created.
If a mistake is made, create a new tag with the corrected name or version number and
document the change in the release notes.

7. Consider using signed tags to provide additional verification of the authenticity of each release.
This can help users trust that they are downloading legitimate code.

1. All usages of release tags should align with the `project` name of the release.
   E.g. if `gateway` artifact is used, the referenced tag **must** be for the `gateway` project.