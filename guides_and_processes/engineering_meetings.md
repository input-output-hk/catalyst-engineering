## Catalyst Engineering Team Meetings
The following is a list of the current recurring development team meetings, their primary purposes, and clear guidelines on what is and is not required for each meeting.

### Meetings
- [Engineering Meeting Structure](#engineering-meeting-structure)
  - [Weekly Meetings](#weekly-meetings)
    - [Monday Technical Meeting](#monday-technical-meeting)
    - [Thursday Technical Meeting](#thursday-technical-meeting)
  - [Daily Meetings](#daily-meetings)
    - [Team Standup](#team-standup)
  - [Bi-Weekly Meetings](#bi-weekly-meetings)
    - [Sprint Demo and Retrospective](#sprint-demo-and-retrospective)
  - [Management Meetings](#management-meetings)
    - [Backlog Grooming](#backlog-grooming-1)
    - [Engineering Management Meeting](#engineering-management-meeting)


### Summary

Meeting matrix for roles, note this is just a high level guide, attendance at meetings is determined by the role of each engineer.

| Meeting                       | Architects         | Product Owner        | Eng. Manager         | Backend Developers            | Frontend Developers           | Designers                           | Design Manager                      | Testers/QA                         | SRE             | Operations       |
|-------------------------------|--------------------|----------------------|----------------------|-------------------------|-------------------------|--------------------------------------|-------------------------------------|-------------------------------------|-----------------|-----------------|
| Standup (Mon-Thu)             | X                  | (Optional)           | X                    | X                       | X                       | (Optional)                           | (Optional)                          | (Optional)                          | (Optional)      | (Optional)      |
| Sprint Demo (End of Sprint)   | X                  | X                    | X                    | X                       | X                       | (Recommended)                        | (Recommended)                       | (Recommended)                       | (Recommended)    | (Recommended)    |
| Sprint Retro (End of Sprint)  | X                  | X                    | X                    | X                       | X                       | X                                    | X                                   | X                                   | (As Required)    | (As Required)    |
| Sprint Planning (Start)       | X                  | X                    | X                    | X                       | X                       | X          | X                        | X             | (As Required)      | (As Required)      |
| Backlog Grooming              | X                  | X                    | X                    | (On Request)| (On Request)| (On Request)             | X           | (On Request)            | (On Request) | (On Request) |
| Tech Discussion (Mon & Thu)   | (Optional)         | (Optional)           | (Optional)           | (Optional)              | (Optional)              | (Optional)                | (Optional)               | (Optional)               | (Optional) | (Optional) |
| Catalyst Team Weekly Meeting   | (Recommended)      | (Recommended)        | (Recommended)        | (Recommended)           | (Recommended)           | (Recommended)                        | (Recommended)                       | (Recommended)                       | (Recommended)    | (Recommended)    |

This matrix provides a high-level guideline. Actual attendance may vary depending on project stage, see the following sections for more details on the purpose of each meeting and guidelines on attendance.

---

### Standup (Daily, ~15 min)

**Purpose:**  
- Quickly daily sync of the engineering team on their current progress, immediate goals, and to identify blockers.

**What to Do:**  
- Each engineer briefly shares what they accomplished since the previous standup, what they plan to do today, and if they have any blockers.
- Keep updates concise and focused on current sprint work.

**What Not to Do:**  
- Avoid deep problem-solving or lengthy discussions.
- Do not introduce unrelated topics or turn it into a full planning session.

**Who Should Attend:**  
- **Mandatory:** Backend Developers, Frontend Developers, Engineering Manager, Architects.  
- **Optional (as needed):** Product Owner, Designers, Design Manager, Testers/QA, SRE, Operations (if actively involved).

**Inputs / Preparation:**  
- Have a clear understanding of your current tasks and any impediments.
- Know what you completed since the last standup.

**Expected Outputs:**  
- Team alignment on daily objectives and awareness of potential blockers.
- Quick hand-offs or follow-up discussions scheduled separately if needed. (Process to be defined in the absence of a scrum master)

**Frequency:**  
- Monday - Thursday (no standup on fridays).


#### Notes for engineers

During the daily standup each engineer should answer the following questions, try not to deviate from these to keep the conversation on topic and focused.

> ##### 📌 Daily Standup Questions
>
> 1. **What did I do since the last standup to achieve the sprint goal?**
> 2. **What will I be working on today?**
> 3. **Do I currently have or foresee any blockers or impediments that will prevent me from completing my current task?**


> #### 💡 **Note**
> In the absence of a scrum master the team should decide how they which to handle blockers and who should te assigned blockers as action items to assist the engineers become unblocked.


---

### Sprint Demo (End of Sprint)

**Purpose:**  
- Showcase the features and improvements completed during the sprint to stakeholders and the team.

**What to Do:**  
- Demonstrate completed, tested, and “Done” work.
- Highlight user-facing changes, performance improvements, or bug fixes.

**What Not to Do:**  
- Do not present **incomplete** or **non-functional** work.
- Avoid lengthy forward-looking discussions; focus on what’s completed now.

**Who Should Attend:**  
- **Mandatory:** Architects, Engineering Manager, Backend & Frontend Developers, Product Owner  
- **Recommended:** Designers, Design Manager, Testers/QA, SRE, Operations
- **Optional:** Other stakeholders who want to see progress

**Inputs / Preparation:**  
- Ensure all demonstration items are ready and accessible.
- Prepare brief talking points or a short walk through for each completed feature.

**Expected Outputs:**  
- Stakeholder feedback on the completed increments.
- Confirmation that delivered work meets acceptance criteria.
- Action items if the deliverable does not meet acceptance criteria or expectation.

**Frequency:**  
- At the end of each sprint (e.g., every 2 weeks).

---

### Sprint Retro (End of Sprint)

**Purpose:**  
- Reflect on the sprint to identify what went well, what didn’t, and how to improve for the next iteration.

**What to Do:**  
- Discuss process improvements, communication issues, and tooling enhancements.
- Agree on actionable steps to improve the next sprint.
- Celebrate the wins.

**What Not to Do:**  
- Avoid blaming each other; focus on processes and systems.
- Do not delve into detailed technical design debates; keep it focused on team efficiency and workflows.

**Who Should Attend:**  
- **Mandatory:** Architects, Engineering Manager, Backend & Frontend Developers, Product Owner, Designers, Design Manager, Testers/QA
- **Recommended:** SRE, Operations (if involved in sprint tasks)

**Inputs / Preparation:**  
- Think about what worked well and what could be better.
- Come prepared with constructive suggestions for improvement.

**Expected Outputs:**  
- A set of action items to improve team processes and collaboration.
- Documented lessons learned to carry forward.
- Action items with an owner to complete any follow up required.

**Frequency:**  
- End of each sprint.

---

### Sprint Planning (Start of Sprint)

**Purpose:**  
- Select, clarify, and commit to a set of “Ready for Dev” items for the upcoming sprint.

**What to Do:**  
- Define high level goal for the sprint.
- Review prioritized backlog items that meet the “Ready” criteria.
- Confirm estimates, acceptance criteria, and dependencies.
- Ensure team capacity aligns with the planned work.

**What Not to Do:**  
- Do not introduce new, unrefined items on the spot.
- Do not create new tickets, tickets at this stage should have been viewed by many people and be in an acceptable state for engineers.
- Avoid deep architectural debates—if needed, schedule a separate tech discussion if required.

**Who Should Attend:**  
- **Mandatory:** Architects, Engineering Manager, Backend & Frontend Developers, Product Owner  
- **Recommended:** Designers, Design Manager (if design tasks are included), Testers/QA (if testing tasks are included)
  
**Inputs / Preparation:**  
- Reviewed and prioritized backlog items.
- Acceptance criteria and estimates in place. (can be completed by engineers separate from meetings)
- Any known dependencies identified.

**Expected Outputs:**  
- A sprint backlog with clearly defined tasks ready to be worked on in the next spring.
- A shared understanding of the sprint goals and commitments.

**Frequency:**  
- Start of each sprint (e.g., every 2 weeks).

---

### Backlog Grooming

**Purpose:**  
- Review candidate tickets/epics that have been prepared to ensure they have clear acceptance criteria, defined scope, and no outstanding dependencies.  
- Discuss estimates and confirm if the size of each task is manageable within a single sprint.  
- Validate that each item aligns with overall product and architectural goals.  
- Prioritize or re-prioritize items based on current project needs and constraints.  
- Identify any items needing further refinement before they can be moved into a “Ready for Dev” state.

**What to Do:**  
- Review candidate tickets/epics, clarify acceptance criteria, confirm estimates.
- Ensure upcoming work is well-defined and aligns with product goals and architectural standards.
- Ensure each task/epic has the minimum required criteria as defined by the team (see separate document)

**What Not to Do:**  
- Do not involve the entire dev team—this is a focused session for shaping work.
- Avoid unrelated technical deep-dives not pertinent to prioritizing and refining tickets.

**Who Should Attend:**  
- **Mandatory:** Architects, Engineering Manager, Product Owner  
- **Optional:** Others may be invited for specific expertise if needed.

**Inputs / Preparation:**  
- Product Owner prepares candidate backlog items.
- Architects/Eng. management review items for feasibility and clarity before the meeting.

**Expected Outputs:**  
- A prioritized and well-defined backlog of items suitable for the next sprint planning, this becomes the runway for engineering and does not need to be limited to just the next sprint, attempt to define a well groomed backlog for up to 3 sprints ahead, any further planning could result in wasted effort if the product direction changes. The length of the engineering runway will be determined by the engineering teams velocity over time.
- Clarity on scope, acceptance criteria, and readiness of items.

**Frequency:**  
- Weekly or Bi-weekly as needed before Sprint Planning, this does not need to align with the sprint cycle. 

---

### Tech Discussion

**Purpose:**  
- Discuss and align on technical challenges, architectural decisions, and implementation approaches.

**What to Do:**  
- Present well-defined technical issues, proposals, or architecture concepts.
- Seek input on technical approaches and finalize decisions where possible.
- Bring forward new ideas, concepts and approaches which can be discussed during the meeting or where preparation work is required at a future Tech Discussion meeting.

**What Not to Do:**  
- This meeting is an open technical discussion to cover all and any topics, it should not be used for planning or scope definition rather it should focus on technical approaches and proposals.

**Who Should Attend:**  
- **Optional (recommended):** Architects, Engineering Manager, Backend/Frontend Developers, Product Owner, Designers, Testers/QA, SRE, Operations.

**Inputs / Preparation:**  
- Prepare relevant documentation, code snippets, or diagrams.
- Have specific questions or proposals ready.

**Expected Outputs:**  
- Wider understanding by the team in relation to the topics discussed during the meeting.

**Frequency:**  
- Weekly (every Monday and Thursday).

---

### Catalyst Team Weekly Meeting

**Purpose:**  
- Provide high-level team updates, project/organizational announcements, and ensure everyone is aligned with the overall direction.

**What to Do:**  
- Share road map updates, upcoming milestones, and any organizational changes.
- Confirm that everyone understands priorities and timelines.

**What Not to Do:**  
- Avoid deep technical or task-level discussions.

**Who Should Attend:**  
- **Recommended:** Everyone

**Inputs / Preparation:**  
- Prepare any necessary high-level announcements as required.

**Expected Outputs:**  
- Shared understanding of the current project state and upcoming changes.
- Clear sense of direction and any organizational announcements communicated.

**Frequency:**  
- Weekly

# Engineering Meeting Structure

- [Engineering Meeting Structure](#engineering-meeting-structure)
  - [Weekly Meetings](#weekly-meetings)
    - [Monday Technical Meeting](#monday-technical-meeting)
    - [Thursday Technical Meeting](#thursday-technical-meeting)
  - [Daily Meetings](#daily-meetings)
    - [Team Standup](#team-standup)
  - [Bi-Weekly Meetings](#bi-weekly-meetings)
    - [Sprint Demo and Retrospective](#sprint-demo-and-retrospective)
  - [Management Meetings](#management-meetings)
    - [Backlog Grooming](#backlog-grooming-1)
    - [Engineering Management Meeting](#engineering-management-meeting)

## Weekly Meetings

### Monday Technical Meeting

- **Attendees:** Engineering Team
- **Purpose:**
  - Discuss technical topics
  - Share knowledge
  - Address challenges

### Thursday Technical Meeting

- **Attendees:** Engineering Team
- **Purpose:**
  - Discuss technical topics
  - Share knowledge
  - Address challenges

## Daily Meetings

### Team Standup
- **Attendees:** Individual Engineering Teams
- **Purpose:**
  - Quick update on daily progress
  - Identify blockers
  - Coordinate tasks

## Bi-Weekly Meetings

### Sprint Demo and Retrospective

- **Attendees:** Engineering Team, Product Team
- **Purpose:**
  - **Demo:**
    - Showcase completed features
    - Gather feedback
  - **Retrospective:**
    - Reflect on the sprint
    - Identify areas for improvement
    - Celebrate successes

## Management Meetings

### Backlog Grooming

- **Attendees:** Engineering Managers, Product Manager
- **Purpose:**
  - Prioritize and refine the backlog
  - Ensure alignment between engineering and product road map

### Engineering Management Meeting

- **Attendees:** Engineering Managers
- **Purpose:**
  - Discuss management-specific topics
  - Address resource allocation
  - Review team performance
  - Manage team dynamics