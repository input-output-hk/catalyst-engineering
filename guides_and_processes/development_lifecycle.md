# Development Lifecycle

> 💡This page documents the development process engineers should follow at your company.
> Helpful for getting new employees up to speed.

- [Development Lifecycle](#development-lifecycle)
  - [Create a branch of the `master` or `main`](#create-a-branch-of-the-master-or-main)
  - [Writing code](#writing-code)
  - [Create a pull request on GitHub](#create-a-pull-request-on-github)
  - [Submit for review](#submit-for-review)

## Create a branch of the `master` or `main`

- In our team, we follow [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow) branch model.
- Name the branch with task GitHub id and short description: `feature/884-finalize-api-approach`
In case of the bug: `bugfix/999-fix-api-error`

## Writing code

- Write cod by following [style guides](https://github.com/input-output-hk/catalyst-engineering#style-guides) and best practices,
- Use [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/#specification),
- Push to the remote branch.

## Create a pull request on GitHub

- In PR description mention the issue which it resolves, e.g. `resolve #884`.
See [this](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue) for more details.
Read more about [GitHub PR](https://github.com/input-output-hk/catalyst-engineering/blob/main/guides_and_processes/ownership.md#github-pr).
- In case it’s possible visually to demonstrate your work, attach images or video.

## Submit for review

Assign the task to the appropriate reviewer.

## Merge approved PR

- merge PR after it's approved
- set item status as 'Ready for QA'
