# Branch Policy

- [Branch Policy](#branch-policy)
  - [Main branch](#main-branch)
  - [Feature branches](#feature-branches)
  - [Pull requests](#pull-requests)
  - [Tagging releases](#tagging-releases)
  - [Hotfixes](#hotfixes)

## Main branch

The `main` branch should always contain the latest stable version of the codebase.
All new features should be developed in feature branches and merged into main through pull requests.

## Feature branches

Feature branches should be created for every new feature or bug fix.****
The naming convention for feature branches should be descriptive and follow a consistent format, such as `feature/{jira-or-github-issue-id}-{name-of-feature}`.
All changes should be made in the feature branch and tested thoroughly before merging into main.

## Pull requests

All changes to the codebase should be made through pull requests.
Pull requests should be reviewed by at least one other team member before merging into main.
Pull requests should include a description of the changes made, any relevant documentation updates, and any required testing.

## Tagging releases

When a release is ready, it should be tagged with a version number.
The version number should follow a consistent format, such as `v{major}.{minor}.{patch}`.To create a new release, create a new tag on the main branch and push it to the remote repository. For more please see [Release policy](guides_and_processes/release_policy.md).

## Hotfixes

If a critical bug is found in the release version, a hotfix branch should be created from the release branch.
The naming convention for hotfix branches should follow a consistent format, such as `hotfix/{jira-or-github-issue-id}-{name-of-bug}`.
The fix should be made in the hotfix branch and tested thoroughly before merging into both the release branch and the main branch