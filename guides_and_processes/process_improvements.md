# Engineering Process Improvements

- [Engineering Process Improvements](#engineering-process-improvements)
  - [PR Review Process](#pr-review-process)
    - [Why We're Improving](#why-were-improving)
    - [How to Implement](#how-to-implement)
    - [What to Expect](#what-to-expect)
      - [Architect/Engineering Management Role](#architectengineering-management-role)
      - [Developer Role](#developer-role)
      - [Review Guidelines](#review-guidelines)
    - [Expected Outcomes](#expected-outcomes)
    - [Note on PR Size](#note-on-pr-size)
  - [Backlog Grooming Improvements](#backlog-grooming-improvements)
    - [Why We're Improving](#why-were-improving-1)
    - [How to Implement](#how-to-implement-1)
    - [What to Expect](#what-to-expect-1)
      - [Management Role](#management-role)
      - [Developer Role](#developer-role-1)
    - [Expected Outcomes](#expected-outcomes-1)

## PR Review Process

### Why We're Improving

- Architects need to review PRs as early as possible and throughout development
- Mitigate risks from:
  - Incorrect assumptions
  - Insufficient specifications
  - Late detection of issues requiring rework
- Enhance review process for large/complex PRs
- Facilitate better knowledge sharing across teams

### How to Implement

1. **Start Early**
   - Create a branch and raise a `draft` PR as soon as you pick up a ticket
   - Include `closes #issue` in the PR description

2. **Regular Updates**
   - Push to your branch at least once daily while working
   - Keep the PR updated with your latest changes

3. **Monitor Tags**
   - Watch for `PR Walk-through` tags on your PR
   - These tags indicate a need for additional review steps

### What to Expect

#### Architect/Engineering Management Role
- Daily review of draft PRs
- Focus on requirement alignment
- Direct communication with developers via Slack if issues are found
- May tag PRs requiring walk-throughs

#### Developer Role
- Focus reviews on "Ready" PRs, not drafts
- If PR is tagged for walk-through:
  - Schedule 1:1 with a peer when PR is ready
  - Conduct live code walk-through

#### Review Guidelines
- Small PRs (1 day or less of work) can skip draft stage
- Other team members should focus on reviewing PRs marked as ready
- Tagged PRs require peer walk-through before final review

### Expected Outcomes

- Early identification of potential issues
- Reduced rework through proactive problem detection
- Enhanced knowledge sharing within development teams
- More efficient review process for both small and large changes

### Note on PR Size

PRs that can be completed in one day or less may proceed directly to review without the draft stage.
This helps maintain efficiency for smaller changes while ensuring proper oversight for larger modifications.


## Backlog Grooming Improvements

### Why We're Improving

- Optimize developer time by reducing meeting overhead
- Enhance backlog grooming quality through focused sessions
- Provide developers more time to review and consider upcoming work
- Create better forums for work discussion

### How to Implement

1. **Restructured Grooming Sessions**
   - Backlog grooming meetings limited to Architects, Engineering Management, and Product
   - Focus on aligning backlog for next sprint
   - Post planned Issues/Epics to Slack after meeting

2. **Team Review Process**
   - Team discussion of Epics/Issues during Thursday Engineering Meeting
   - 24-hour window for developers to review before discussion
   - Dedicated time for questions and alignment

### What to Expect

#### Management Role

- Focus on backlog refinement and prioritization
- Collaborative improvement of epics/issues
- Prepare clear communication of upcoming work

#### Developer Role

- Reduced meeting attendance
- More time for focused development work
- 24-hour window to review upcoming work
- Structured forum for questions and discussion

### Expected Outcomes

- Increased developer productivity through:
  - Reduced meeting time
  - Better work preparation
  - Improved async communication
- Enhanced backlog quality through:
  - Focused management attention
  - Dual-purpose grooming sessions
  - Better team understanding
- More efficient use of engineering management time by:
  - Combining grooming and prioritization
  - Improving epic/issue quality before team presentation
  - Streamlining communication processes