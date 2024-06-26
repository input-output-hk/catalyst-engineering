# Ownership Policy for Software Engineers

- [Ownership Policy for Software Engineers](#ownership-policy-for-software-engineers)
  - [Jira/GitHub Ticket](#jiragithub-ticket)
  - [GitHub PR](#github-pr)
  - [GitHub Issue State](#github-issue-state)
  - [Handover of Ownership](#handover-of-ownership)

At our organization, we believe in empowering our software engineers to take ownership of the work they do.
This ownership policy outlines the guidelines for software engineers with regards to Jira/GitHub tickets and GitHub pull request (PR) handling.

## Jira/GitHub Ticket

When a Jira/GitHub ticket is assigned to you, you become the owner of that ticket
until it is marked as "done" or "closed."

As the owner of the ticket, you are responsible for:

* Reviewing the ticket thoroughly to understand the requirements
* Providing accurate estimates for completion
* Updating the ticket regularly to reflect progress made and notify the team and stakeholder of any issues or blockers
* Seeking help when required to ensure timely resolution
* Ensuring that the ticket is resolved to the requirements of the product owner and stakeholders
* Ensuring the code meets the coding standards and requirements set by the team
* Ensuring the code is properly documented
* Resolving any issues or bugs that are discovered during testing or after deployment
* When PR is merged, the ticket should be marked as "done" or "closed". The url to the PR should be added to the ticket's comment.

## GitHub PR

When a GitHub pull request is created, the author of the pull request becomes the owner of that code until it is merged into the main branch.
As the owner of the pull request, you are responsible for:

* We encourage the use of the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
format for PR titles and commit messages.
* PR title should pass conventional commit linting.
* Providing a clear description of the changes made and the purpose of the code
* Assign yourself as the PR owner
* Assigning the appropriate reviewers to the PR
* Use GitHub [labels](https://github.com/input-output-hk/catalyst-core/labels) to categorize the PR
* Ensuring that the code is properly reviewed by other team members
* Addressing any feedback or comments provided by the reviewers

Once the pull request is merged, ownership of the code is transferred to the team as a whole,
and any further changes or updates will be managed through the Jira/GitHub ticket process.

## GitHub Issue State

GitHub issues should be used to track bugs, enhancements,
tasks or any other work items for a [project](https://github.com/orgs/input-output-hk/projects/102/views/2).
The state of an issue indicates its current status in the development process.

- **New**: A new issue that has been created but not yet triaged or assigned.
- 📋 **Backlog**: An issue that has been triaged and is ready to be worked on, but not yet assigned to a developer.
- 🔖 **Ready**: An issue that has been assigned to a developer and is ready to be worked on.
- 🏗 **In progress**: An issue that is currently being worked on by a developer.
- 👀 **In review**: An issue that has been completed by a developer and is awaiting review.
- 🔬 **Ready For QA**: An issue that has been reviewed, merged and is ready for testing by the QA team.
- ✅ **Done**: An issue that has been completed and closed.
- 🛑 **Blocked** An issue that cannot be progressed due to a blocker or dependency.

## Handover of Ownership

Software engineers may need to handover ticket or PR ownership for various reasons,
such as taking a break, leaving the organization, or workload management.

**In such cases, the following guidelines must be followed:**

* The engineer must inform the team lead or manager in advance and provide relevant context and documentation.
* The handover should be done in a structured manner, including a handover document that outlines the status,
next steps, and any pending work.
* The new owner should be given sufficient time and resources to familiarize themselves with the ticket or PR.