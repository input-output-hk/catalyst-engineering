# Catalyst channels

Catalyst repos have the following channels, in increasing order of stability.

**main**

The current tip-of-tree, absolute latest cutting edge build. Usually functional, though sometimes we accidentally break things.

**beta**

We will branch from main for a new beta release at the end of the the sprint.
This branch will then be "stabilized" for the next couple of weeks,
meaning we will accept cherrypick requests for high impact issues. As we near the end of the month and the next beta branch,
we will likely reduce the number of cherrypicks we are willing to do.
Once a month, the beta branch will live on to become the next stable branch, as detailed below.

**stable**

Roughly once a month, a branch that has been stabilized on beta will become our next stable branch and we will create a stable release from that branch.
We recommend that you use this channel for all production app releases.
In case of high severity, high impact or security issues, we may do a hotfix release for the stable channel.
This will follow the same cherrypick process.