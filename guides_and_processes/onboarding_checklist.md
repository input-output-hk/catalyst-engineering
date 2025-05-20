# Onboarding checklist

- [Overview](#overview)
- [Staying in touch](#staying-in-touch)
- [Git repositories](#git-repositories)
- [Setting up the workspace](#setting-up-the-workspace)
    - [Common tools](#common-tools)
    - [Frontend tools](#frontend-tools)
    - [Backend tools](#backend-tools)

## Overview

This document serves as a starting point for the Catalyst developers to learn the Catalyst processes and setup their workspace. Some of the recommendations may be out of date, so the improvement and updates are expected to be performed occasionally.  

## Staying in touch

Upon entering the project make sure to join these **Slack** channels:

- [cat-tribe-all](https://input-output-rnd.slack.com/archives/C037BCPTKBN) – an internal source of general news related to Catalyst projects.
- [catalyst-backend](https://input-output-rnd.slack.com/archives/C088D6HMPMM) – backend (Rust) developer channel for specialized technical discussions.
- [catalyst-core](https://input-output-rnd.slack.com/archives/C0379A6DZKK) – team activity notifications channel; a place to report PTO and sick days to.
- [catalyst-eng-knowledge-hub](https://input-output-rnd.slack.com/archives/C06E6659USG) – a place to share tech news and blog posts.
- [catalyst-engineering](https://input-output-rnd.slack.com/archives/C04H3D237DF) – joint space to discuss technical topics, ask for assistance, share knowledge and alert engineers.
- [catalyst-forge](https://input-output-rnd.slack.com/archives/C07SRNR9EU9) – for discussions, feature requests, and help with Catalyst Forge.
- [catalyst-review-me](https://input-output-rnd.slack.com/archives/C06EM1744BX) – posting pull requests here lets developers notice them easier and can speed up review process.
- WIP.

Team meetings happen via the **Google Meet**, scheduled in the **Google Calendar**.

- [meeting_policy](meeting_policy.md) – communication and collaboration on the meetings.
- [engineering_meetings](engineering_meetings.md) – current recurring development team meetings; practical guidelines.

Also, daily meetings of the Catalyst Core are lead by developers themselves, switching every meeting in a cycle. When it's your turn, you'll want to share your screen and open **GitHub Projects** board:

- [input-output-hk/Projects/Catalyst](https://github.com/orgs/input-output-hk/projects/102/views/2?filterQuery=iteration%3A%40current%2C%40previous) – the board showing progress on the last two iterations.

And to know **when** is your turn to lead the daily meeting, consult:

> TODO: link to where is the dev queue.

## Git repositories

Git is the version control system of choice, with the Catalyst repositories hosted online at [input-output-hk](https://github.com/input-output-hk) on GitHub. Since the code is spread across a vast number of repos, some **notable mentions** should be made:

- [catalyst-engineering](https://github.com/input-output-hk/catalyst-engineering) – home to the learning resources and guides such as this one.
- [catalyst-core](https://github.com/input-output-hk/catalyst-core) – the legacy Catalyst stack that's currently running in production; major parts of it are currently being upgraded and rewritten to [catalyst-voices](https://github.com/input-output-hk/catalyst-voices) and [catalyst-libs](https://github.com/input-output-hk/catalyst-libs).
    - [jormungandr](https://github.com/input-output-hk/catalyst-core/tree/main/src/jormungandr) (Rust) – a node implementation, aimed to support the Ouroboros type of consensus protocol.
- [catalyst-voices](https://github.com/input-output-hk/catalyst-voices) – the replacement Catalyst stack that's currently in development.
    - [catalyst-gateway](https://github.com/input-output-hk/catalyst-voices/tree/main/catalyst-gateway) (Rust) – the backend of the Catalyst Voices hosted stack.
    - WIP.
- [catalyst-libs](https://github.com/input-output-hk/catalyst-libs) – unified codebase for the Catalyst project.
    - [catalyst-voting](https://github.com/input-output-hk/catalyst-libs/tree/main/rust/catalyst-voting) (Rust) – in-progress replacement for [chain-vote](https://github.com/input-output-hk/catalyst-core/tree/main/src/chain-libs/chain-vote) and [chain-crypto](https://github.com/input-output-hk/catalyst-core/tree/main/src/chain-libs/chain-crypto) from [catalyst-core](https://github.com/input-output-hk/catalyst-core).
    - [rbac-registration](https://github.com/input-output-hk/catalyst-libs/tree/main/rust/rbac-registration) (Rust) – registration mechanism reinvented utilizing RBAC.
    - [signed_doc](https://github.com/input-output-hk/catalyst-libs/tree/main/rust/signed_doc) (Rust) – Catalyst signed document implementation.
    - WIP.
- [hermes](https://github.com/input-output-hk/hermes) – unified codebase for the Hermes engine.

> TODO: link branch policies, code reviews, refactoring, etc.

## Setting up the workspace

Recommended **tools** for running Catalyst executables, performing lints, pre-push checks and cohesive development experience overall.

### Common tools

Regardless of what is the task at hand, some tools are general enough within the project to be worth installment:

- [vscode](https://github.com/VSCodium/vscodium) – although an editor is in the end the developer's choice, a lot of Catalyst repositories contain curated dot files for Visual Studio Code and advise for using it by default.

---
---
---
---
---
---
> TODO: add Docker and Earth and Just. Provide examples from <https://github.com/input-output-hk/catalyst-voices/tree/main/catalyst-gateway>.

### Frontend tools

> TODO: add flutter with a minimal non-dummy desc.

### Backend tools

> TODO: add rustup and mention what version are we running.

> TODO: add scylla marked (Optional). Link to existing local guidelines https://github.com/input-output-hk/catalyst-voices/tree/main/utilities/local-scylla.

> TODO: add other locals.
