# On-Call Policy

- [On-Call Policy](#on-call-policy)
  - [Objective](#objective)
  - [Selection of On-Call Personnel](#selection-of-on-call-personnel)
  - [Duration and Rotation](#duration-and-rotation)
  - [Response Times](#response-times)
  - [Resolution Times](#resolution-times)
      - [Urgent Issues](#urgent-issues)
      - [High-Priority Issues](#high-priority-issues)
      - [Medium-Priority Issues](#medium-priority-issues)
      - [Low-Priority Issues](#low-priority-issues)
    - [Guidelines and Expectations](#guidelines-and-expectations)
  - [Communication Tools](#communication-tools)
  - [Incident Reporting](#incident-reporting)
  - [Escalation](#escalation)
  - [Backup \& Redundancy](#backup--redundancy)
  - [Feedback Loop](#feedback-loop)

## Objective

Ensure the Catalyst project's uninterrupted functioning by swiftly identifying and addressing technical issues,
minimizing potential downtime or disruptions to the Cardano community.

## Selection of On-Call Personnel

- Rotate on-call responsibilities among team members to prevent burnout.
- Ensure team members have the necessary access and permissions to handle incidents.

## Duration and Rotation

- On-call rotations typically last one week but adjust based on team size and preferences.
- Avoid consecutive weeks of on-call duties for any single team member.

## Response Times

- Urgent Issues (e.g., node down, network disruptions): Respond within 15 minutes.
- High Priority (e.g., minor glitches, API issues): Respond within 30 minutes.
- Medium/Low Priority (non-critical updates, minor queries): Respond within 1-4 hours.

## Resolution Times

#### Urgent Issues

- **Description**: System outage, data breaches, or any malfunction affecting all users or the entire platform.
- **Expected Resolution Time**: Within 1 hour of the alert. If a full resolution is not possible, a temporary fix or workaround should be implemented.

#### High-Priority Issues

- **Description**: Major features not working, impacting a large portion of users but not resulting in a complete system outage.
- **Expected Resolution Time:** Within 2 hours of the alert.


#### Medium-Priority Issues

- **Description**: Minor features not working or performance issues affecting a subset of users.
- **Expected Resolution Time:** Within 4 hours of the alert.

#### Low-Priority Issues

- **Description:** Cosmetic issues, minor bugs, non-urgent improvements or patches.
- **Expected Resolution Time**: Within 12 hours or by the next working day.

### Guidelines and Expectations

- **Communication**: If the on-call engineer cannot resolve an incident within the expected resolution time, they should promptly communicate this to both their team lead and the affected stakeholders, explaining the situation and providing an updated timeline.

- **Escalation**: Should the primary on-call engineer be unable to address an incident within the expected response time, it should be escalated to the secondary on-call engineer or the designated escalation point.

- **Documentation**: All incidents, regardless of their severity, should be documented in the incident log, detailing the issue, resolution steps taken, resolution time, and any other pertinent information.

- **Post-Incident Review**: For Critical and High-Priority issues, a post-incident review should be conducted within 48 hours of the issue's resolution to analyze the root cause, evaluate the effectiveness of the response, and identify areas for improvement.

- **Feedback and Continuous Improvement**: On-call engineers are encouraged to provide feedback on the resolution process and suggest ways to improve it. This feedback will be reviewed periodically to enhance our on-call procedures and training.

## Communication Tools

- Utilize Slack's dedicates channels for real-time communications.
- For urgent issues, consider using phone calls or SMS to reach the on-call person.
- For structured reporting and incident logging, use Jira or GitHub.

## Incident Reporting

- Clearly describe the issue, its impact, potential causes, and any immediate mitigation steps taken.
- Record all incident details for post-mortem analysis.

## Escalation

- If an on-call engineer cannot resolve an issue within a set period (e.g., 1 hour), escalate to a senior engineer or team lead
- Have a list of contacts for different expertise areas.

## Backup & Redundancy

- Always have a backup on-call person in case the primary engineer is unavailable.
- Consider having redundant setups for critical systems or nodes to ensure availability.

## Feedback Loop

- Post-mortem after every major incident to identify root causes and prevent recurrence.
- Regular reviews of on-call incidents, looking for patterns and potential improvements.
