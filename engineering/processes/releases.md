# Releases and versioning

This document describes the current release and versioning strategy.
This strategy is likely to change as Catalyst's systems matures.

- [Releases and versioning](#releases-and-versioning)
  - [Backend](#backend)
    - [Release Cadence](#release-cadence)
    - [Library versioning and release cadence](#library-versioning-and-release-cadence)
    - [Data and communication versioning](#data-and-communication-versioning)
    - [Releases](#releases)
  - [Frontend](#frontend)

## Backend

### Release Cadence

New backend versions are released every two weeks (each sprint).
Sometimes we do out-of-schedule patch releases.

### Library versioning and release cadence

Each release include new versions of:

- All Rust crates
- All Python packages

We use semantic versioning. All versions are increased in lockstep, with a minor version bump each time (0.1.0, 0.2.0, 0.3.0, …).

This means we might add breaking changes in each new release.

In rare cases we will do patch releases, e.g. 0.3.1, when there is a critical bug fix.

These patch releases will not contain any breaking changes.

We sometimes do pre-releases. Then we use the versioning 0.2.0-alpha.0 etc.

### Data and communication versioning

We have not yet committed to any backwards or forwards compatibility.

### Releases

Release builds and triggered by pushing a release tag to GitHub in the form v0.2.0.
If we are doing a patch release, we do a branch off of the latest release tag (e.g. v0.3.0) and cherry-pick any fixes we want into that branch.

## Frontend

- TODO: Add frontend release strategy