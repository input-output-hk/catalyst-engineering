# Code Reviews

- [Code Reviews](#code-reviews)
  - [Introduction](#introduction)
  - [Preparing Code for Review](#preparing-code-for-review)
    - [Commit Messages](#commit-messages)
    - [PR Descriptions and Titles](#pr-descriptions-and-titles)
      - [PR Title](#pr-title)
      - [PR description example](#pr-description-example)
  - [Performing Code Reviews](#performing-code-reviews)
    - [Summary](#summary)
  - [Speed of Code Reviews](#speed-of-code-reviews)
    - [Why Should Code Reviews Be Fast?](#why-should-code-reviews-be-fast)
    - [How Fast Should Code Reviews Be?](#how-fast-should-code-reviews-be)

## Introduction

A code review is a process where someone other than the author(s) of a piece of code examines that code.
We use code review to maintain the quality of our code and products.
This documentation is the description of our code review processes and policies.

## Preparing Code for Review

Preparation sets your reviewers up for success.

### Commit Messages

Make sure your commit messages are descriptive.

### PR Descriptions and Titles

#### PR Title

Make sure PR title is [conventional](https://www.conventionalcommits.org/en/v1.0.0/#specification):

`feat:Short description of the PR`

`refactor:Short description of the PR`

`ci: Short description of the PR`

#### PR description example
```md
# Description

Thanks for contributing to the project!
Please fill out this template to help us review your changes.

## Related Issue(s)

List the issue numbers related to this pull request.

> e.g., Closes #123, Resolves #456  Fixes #367

## Description of Changes

Provide a clear and concise description of what the pull request changes.

## Breaking Changes

Describe any breaking changes and the impact.

## Screenshots

If applicable, add screenshots to help explain your changes.

## Related Pull Requests

If applicable, list any related pull requests.

> e.g., #123, #456

## Please confirm the following checks

* [ ] My code follows the style guidelines of this project
* [ ] I have performed a self-review of my code
* [ ] I have commented my code, particularly in hard-to-understand areas
* [ ] I have made corresponding changes to the documentation
* [ ] My changes generate no new warnings
* [ ] I have added tests that prove my fix is effective or that my feature works
* [ ] New and existing unit tests pass locally with my changes
* [ ] Any dependent changes have been merged and published in downstream module
```

## Performing Code Reviews

Code reviews should look at:

**Design**: Is the code well-designed and appropriate for your system?

**Functionality**: Does the code behave as the author likely intended? Is the way the code behaves good for its users?

**Complexity**: Could the code be made simpler? Would another developer be able to easily understand and use this code when they come across it in the future?

**Tests**: Does the code have correct and well-designed automated tests?

**Naming**: Did the developer choose clear names for variables, classes, methods, etc.?

**Comments**: Are the comments clear and useful?

**Style**: Does the code follow our [style guides](https://github.com/input-output-hk/catalyst-engineering#style-guides)?

**Documentation**: Did the developer also update relevant documentation?

### Summary

In doing a code review, you should make sure that:

- The code is well-designed.
- The functionality is good for the users of the code.
- Any UI changes are sensible and look good.
- Any parallel programming is done safely.
- The code isn’t more complex than it needs to be.
- The developer isn’t implementing things they might need in the future but don’t know they need now.
- Code has appropriate unit tests.
- Tests are well-designed.
- The developer used clear names for everything.
- Comments are clear and useful, and mostly explain why instead of what.
- Code is appropriately documented (generally in g3doc).
- The code conforms to our style guides.

Make sure to review every line of code you’ve been asked to review, look at the context, make sure you’re improving code health, and compliment developers on good things that they do.

## Speed of Code Reviews

**We optimize for the speed at which a team of developers can produce a product together**,
as opposed to optimizing for the speed at which an individual developer can write code.
The speed of individual development is important, it’s just not as important as the velocity of the entire team.

### Why Should Code Reviews Be Fast?

When code reviews are slow, several things happen:

- **The velocity of the team as a whole is decreased**. Yes, the individual who doesn’t respond quickly to the review gets other work done. However, new features and bug fixes for the rest of the team are delayed by days, weeks, or months as each CL waits for review and re-review.

- **Developers start to protest the code review process**. If a reviewer only responds every few days, but requests major changes to the CL each time, that can be frustrating and difficult for developers. Often, this is expressed as complaints about how “strict” the reviewer is being. If the reviewer requests the same substantial changes (changes which really do improve code health), but responds quickly every time the developer makes an update, the complaints tend to disappear. **Most complaints about the code review process are actually resolved by making the process faster.**

- **Code health can be impacted**. When reviews are slow, there is increased pressure to allow developers to submit CLs that are not as good as they could be. Slow reviews also discourage code cleanups, refactoring, and further improvements to existing CLs.

### How Fast Should Code Reviews Be?

If you are not in the middle of a focused task, **you should do a code review shortly after it comes in**.

**One business day is the maximum** time it should take to respond to a code review request (i.e., the first thing the following day).

Following these guidelines means that a typical PR should get multiple rounds of review (if needed) within a single day.
