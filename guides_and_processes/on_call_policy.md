# On-Call Policy

- [On-Call Policy](#on-call-policy)
  - [Objective:](#objective)
  - [Selection of On-Call Personnel](#selection-of-on-call-personnel)
  - [Duration and Rotation](#duration-and-rotation)
  - [Response and Resolution Times](#response-and-resolution-times)
  - [Communication Tools](#communication-tools)
  - [Incident Reporting](#incident-reporting)
  - [Escalation](#escalation)
  - [Backup \& Redundancy](#backup--redundancy)

## Objective:

Ensure the Catalyst project's uninterrupted functioning by swiftly identifying and addressing technical issues,
minimizing potential downtime or disruptions to the Cardano community.

## Selection of On-Call Personnel

- Rotate on-call responsibilities among team members to prevent burnout.
- Ensure team members have the necessary access and permissions to handle incidents.

## Duration and Rotation

- On-call rotations typically last one week but adjust based on team size and preferences.
- Avoid consecutive weeks of on-call duties for any single team member.

## Response and Resolution Times

- Urgent Issues (e.g., node down, network disruptions): Respond within 15 minutes.
- High Priority (e.g., minor glitches, API issues): Respond within 30 minutes.
- Medium/Low Priority (non-critical updates, minor queries): Respond within 2-4 hours.

##  Communication Tools

- Utilize Slack's dedicates channels for real-time communications.
- For urgent issues, consider using phone calls or SMS to reach the on-call person.
- For structured reporting and incident logging, use Jira or GitHub.

## Incident Reporting

- Clearly describe the issue, its impact, potential causes, and any immediate mitigation steps taken.
- Record all incident details for post-mortem analysis.

## Escalation

- Establish an escalation path, including contacts within IOHK or other Cardano-associated organizations if needed.
- Define a clear escalation timeframe if the primary on-call person cannot address the issue.

## Backup & Redundancy

- Always have a backup on-call person in case the primary engineer is unavailable.
- Consider having redundant setups for critical systems or nodes to ensure availability.
