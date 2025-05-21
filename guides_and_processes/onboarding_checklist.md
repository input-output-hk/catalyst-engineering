# Onboarding checklist

- [Overview](#overview)
- [Staying in touch](#staying-in-touch)
- [Git repositories](#git-repositories)
- [Setting up the workspace](#setting-up-the-workspace)

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

- [stand_up](https://gist.github.com/minikin/1f9c9019ce3a856253f44a3056103b7b) – a text document listing developers in a queue for the stand up activity; it is also linked as a bookmark in the [catalyst-engineering](https://input-output-rnd.slack.com/archives/C04H3D237DF) Slack channel.

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

On that topic, there are few resources that delve into things to keep in mind **when contributing**:

- [development_lifecycle](development_lifecycle.md) – what are the steps from writing code to merging it upstream.
- [branch_policy](branch_policy.md) – short rundown of rules regarding branches and pull requests.
- [code_reviews](code_reviews.md) – how to prepare for code review and how to perform it.
- [release_policy](release_policy.md) – conventions with regards to git tags.

Regarding **Github issues**. As mentioned in [previous section](#staying-in-touch), **GitHub Projects** is the main source of tracking development progress. To that end, some extra attention should be paid when interacting with issues and pull requests:

- [issue_policy](issue_policy.md) – Catalyst policy for managing GitHub issues.
- [ownership](ownership.md) – guidelines with regards to GitHub issue and pull request handling.

## Setting up the workspace

**Recommended tools** for running Catalyst executables, performing lints, pre-push checks and cohesive development experience overall.

Regardless of what is the task at hand, some tools are general enough within the project to be worth installment:

- [vscode](https://github.com/VSCodium/vscodium) – although an editor is in the end the developer's choice, a lot of Catalyst repositories contain curated dot files for Visual Studio Code and advise for using it by default.
- [just](https://github.com/casey/just) – a tool similar to [GNU Make](https://www.gnu.org/software/make) that can remove some command line boilerplate; the majority if not all Catalyst repositories maintain the special Justfiles in order for [just](https://github.com/casey/just) to be always an available option for running the apps.

Then, a few **containerization** tools that are widely across Catalyst. Although not always essential, they allow you to run Catalyst executables consistently and to manually test the effect of your updates outside of your local environment.

- [docker](https://docs.docker.com/get-started/get-docker) – the cornerstone dependency of other tools in this section.
- [docker-compose](https://docs.docker.com/compose/install) – lets you spin up executables from built images; if you concede to install [docker](https://docs.docker.com/get-started/get-docker), you probably want to install that too.
- [earthly](https://docs.earthly.dev/install) – Earthly serves a central role in the CI process and is the primary orchestrator along with Github Actions; moreover, there is a [dedicated Catalyst CI onboarding guide](https://github.com/input-output-hk/catalyst-ci/blob/f694dda57245c7fa44e3f6b7ea631cbbf63feab7/docs/src/onboarding/index.md).

Moving on to the **backend tools**. For Rust developers, it boils down to:

- [rustup](https://www.rust-lang.org/tools/install) – installs and manages Rust toolchain; it is important to keep your local toolchain on par with the upstream one; nightly toolchain is recommended to use for formatting and clippy, while stable is used for building.

Finally, you would need to set up **more specific tools** for local development, depending on the repository you are working in. These usually have their own dedicated guides:

- [catalyst-voices/utilities](https://github.com/input-output-hk/catalyst-voices/tree/main/utilities) - will help you with run the integration tests locally and setting up [Scylla](https://www.scylladb.com) database and a local Kubernetes cluster.
