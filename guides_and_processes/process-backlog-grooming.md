# Engineering Backlog Grooming

## Supporting definitions for Milestones, Epics, and Tasks

### Milestones

- **Key Progress Points:** Represent significant deliverable of value to the Catalyst platform or key events in the project timeline. In the context of the Catalyst road map a milestone can be associated with one release cycle. 
- **Phase Completion:** Used to mark the completion of major project phases or deliverables. A milestone is not considered complete until all associated Epics are in the completed status.

**Attributes:**
- **Name:** A clear and descriptive title for the milestone.
- **Description:** A brief overview of what the milestone entails and its significance.
- **Due Date:** The target date for achieving the milestone.
- **Associated Epics:** A list of epics that contribute to reaching the milestone.
- **Status:** Current state of the milestone (e.g., Planned, In Progress, Completed).
- **Owner:** The individual or team responsible for ensuring the milestone is achieved.
- **Dependencies:** Any milestones that must be completed or external dependencies before this milestone can be achieved.


### Epics

- **Large Bodies of Work:** Encompass multiple related tasks and provide a high-level overview of significant features or initiatives.
- **Structure:** Serve as containers for related user stories or tasks, helping to organize and prioritize work effectively.Each Epic must be associated with only one Milestone.
- **Completion** Completion of an epic indicates the completion of all associated user stories and tasks. An epic can not be considered complete unless all associated user stories and tasks are in the complete state.

**Attributes:**
- **Name:** A clear and descriptive title for the epic.
- **Description:** A detailed explanation of the epic’s objectives and scope and how it fulfills the requirements of the Milestone.
- **Associated Milestone:** The milestone that the epic contributes to.
- **Related Tasks/User Stories:** A list of tasks or user stories that fall under the epic.
- **Priority:** The importance level of the epic within the project (e.g., High, Medium, Low), Low priority epics can move to subsequent milestones.
- **Status:** Current state of the epic (e.g., Planned, In Progress, Completed).
- **Owner:** The individual or team responsible for managing and executing the epic.
- **Estimated Effort:** An estimate of the total effort required to complete the epic (not required up front and can be the sum of all sub tasks or user stories defined in the epic)
- **Dependencies:** Any epics, milestones or external dependencies that must be completed before this epic can be addressed.


### Tasks

- **Individual Action Items:** Specific, actionable units of work that contribute to the completion of an epic, the scope of a task should be such that it can be completed by a single engineer within the time bounds of a single sprint.
- **Purpose:** Tasks must have clearly defined goals, scope, and acceptance criteria to ensure completion by engineers.

**Attributes:**
- **Name:** A concise and descriptive title for the task.
- **Description:** A detailed explanation of what the task entails, its scope, external dependencies and systems, and supporting documentation.
- **Assigned To:** The team member responsible for completing the task. (not required during definition)
- **Priority:** The importance level of the task within the epic or sprint (e.g., High, Medium, Low).
- **Status:** Current state of the task (e.g., New, Backlog, Ready For Development, In Progress, In Review, Done, Blocked).
- **Estimated Effort:** An estimate of the time or story points required to complete the task. (Defined by the engineering team)
- **Acceptance Criteria:** Specific conditions that must be met for the task to be considered complete, tasks that to not pass all acceptance criteria functional or non functional will be considered incomplete.
- **Dependencies:** Any tasks or external factors that must be addressed before this task can be started or completed.
- **Due Date:** The target date for completing the task.
- **Labels/Tags:** Categorization labels such as feature, bug, documentation, etc., to aid in organization and filtering.
- **Iteration/Sprint:** The sprint or iteration in which the task is planned to be completed.
- **Area:** The specific component or module of the project that the task relates to. (Architects to define a list of components across the system)
- **Attachments/Links:** References to related documents, designs, or resources necessary for completing the task.




## Backlog grooming pre-requisites

Prior to backlog grooming **Milestones**, **Epics**, and **Tasks** must be defined, this is an iterative process and  **Milestones**, **Epics**, and **Tasks** may go through a number of iterations before being accepted. The following definitions and workflow is used to support the backlog grooming process to ensures that each level of work is appropriately scoped, reviewed, and meets the necessary criteria before advancing to the next stage and ultimately into the development backlog. In the absence of a dedicated scrum master, at each stage an owner(s) should be identified that will be responsible for ensuring the completeness at each stage. While the process provides structure, it remains flexible to accommodate change.

---

### Workflow Overview

1. **Milestone Definition**
2. **Epic Definition**
3. **Task Definition**
4. **Progression Criteria**

---

### 1. Milestone Definition

**Purpose:**  
Milestones represent the next major achievement or significant progress point in the project road map.

**Owner:**  
- **Product Owner (PO)**

**When/How Defined:**  
- Identified during strategic planning sessions and can be defined in advance of starting.
- Reflects key project phases or deliverables, the focus can be technology or business focused or can be across all concerns relating to the Catalyst platform and eco-system.

**Criteria Before Moving to Next Stage:**  
- **Clear Objective:** The milestone clearly defines a significant achievement.
- **Alignment with Product Goals:** Ensures the milestone supports overall product vision and objectives.
- **Feasibility:** Assessed by Product Owner, Architects, Designers and Engineering Managers to determine the feasibility of the milestone scope as a deliverable.

**Status:** 
- **Draft:** Initial draft of a milestone where the scope and goals have not yet been agreed.
- **Acceptance:** Ready for final acceptance by all stakeholders before it moves to the next phase.
- **In Progress:** Once accepted a milestone is in progress, a milestone has a delivery date but does not have a start date, work can start on a milestone well in advance of delivery if required.
- **Delivery:** Once all Epics associated with a milestone have been moved to the completed status the Milestone moves to the Delivery status. 
- **Complete:** Once all deliverables of a milestone have been completed and the milestone has been accepted by the stakeholders the milestone can move into the complete status.

**Note:** Git hub projects does not have status for Milestones (consider another approach here if required)
 
---

### 2. Epic Definition

**Purpose:**  
Epics break down milestones into high-level, manageable components that encapsulate significant features or initiatives.

**Defined By:**  
- **Architects**
- **Designers**
- **Product Owner (PO)**

**When/How Defined:**  
- After a milestone is established.
- During planning sessions involving architects, designers, and the PO (other expertise may be required at various times). 

**Criteria Before Moving to Next Stage:**  
- **High-Level Breakdown:** Epics should provide a broad overview of the work required to achieve the milestone.
- **Scope Definition:** Clearly outlines the boundaries and objectives of the epic.
- **Alignment with Milestone:** Ensures each epic contributes directly to the milestone’s achievement.
- **Initial Feasibility Assessment:** Evaluation to confirm that the epic is actionable and aligns with architectural standards.

**Status:**

- 📋 **Backlog** Epics that have been identified but are not yet prioritized or refined for development. These epics are waiting to be reviewed and moved into the **Ready** status.
- 🔖 **Ready** Epics that have been refined, prioritized, and meet the criteria to be worked on in upcoming sprints.
- 🏗 **In Progress** Epics that are currently being actively worked on by the development team.
- 👀 **In Review** Epics that have been completed by the development team and are now awaiting review.
- 🔬 **Ready For QA** Epics that have passed the review stage and are ready for Quality Assurance testing.
- ✅ **Done** Epics that have been fully completed, tested, and meet all acceptance criteria. They are ready for deployment or have already been deployed.
- 🛑 **Blocked** Epics that cannot proceed due to impediments. These items are stalled until the blocking issue is resolved.

---


### 3. Task Definition

**Purpose:**  
Tasks are the individual, actionable units of work that contribute to the completion of epics. They can be specific to frontend, backend, SRE, testing, etc.

**Defined By:**  
- **Architects**
- **Developers (Frontend, Backend, SRE)**
- **Testers/QA**
- **Designers (if applicable)**

**When/How Defined:**  
- After epics are established.
- During sprint planning or backlog refinement sessions.
- Task breakdown does not have to happen within any of the process meetings and can be done offline.

**Criteria Before Moving to Next Stage:**  
- **Specific and Actionable:** Each task should have a clear, defined action.
- **Assigned Ownership:** Clearly assigned to a team member responsible for ensuring the task is well defined, this is not the same as the implementation of the task.
- **Acceptance Criteria:** Defined conditions that must be met for the task to be considered complete.
- **Estimation:** Time or story points estimated to gauge effort. (Current minimum is 1 day)
- **Dependencies:** Any dependencies on other tasks or external factors are noted.

**Status:**

- 📋 **Backlog** Tasks that have been identified but are not yet prioritized or refined for development. These tasks are waiting to be reviewed and moved into the **Ready** status.
- 🔖 **Ready** Tasks that have been refined, prioritized, and meet the criteria to be worked on in upcoming sprints.
- 🏗 **In Progress** Tasks that are currently being actively worked on by the development team.
- 👀 **In Review** Tasks that have been completed by the development team and are now awaiting review.
- 🔬 **Ready For QA** Tasks that have passed the review stage and are ready for Quality Assurance testing.
- ✅ **Done** Tasks that have been fully completed, tested, and meet all acceptance criteria. They are ready for deployment or have already been deployed.
- 🛑 **Blocked** Tasks that cannot proceed due to impediments. These items are stalled until the blocking issue is resolved.



## Backlog Grooming Process

Backlog Grooming is a crucial activity to ensures our **Milestones**, **Epics**, and **Tasks** are well-defined, prioritized, and ready for development. This process involves collective refinement and validation of Epics and tasks to maintain an actionable backlog with sufficient runway to accommodate the engineers velocity but not so long as to waste preparation effort if the product direction shifts.


### Roles and Responsibilities

- **Product Owner (PO):**
  - Defines the product milestones. 
  - Prepares and prioritizes backlog Epics and Tasks when required.
  - Ensures that milestones align with product goals.
  
- **Architects:**
  - Validate the technical feasibility of epics and tasks.
  - Breaks down milestones in to epics and tasks in collaboration with engineering, design and the product owner.
  - Ensure alignment with architectural standards and principles.
  
- **Designers & Design Manager:**
  - Provide input on design-related epics and tasks.
  - Ensure design consistency and adherence to user experience standards.
  
- **Engineering Manager:**
  - Facilitates the grooming sessions.
  - Ensures that the backlog reflects the team's capacity and priorities.
  
- **Developers (Backend, Frontend, SRE):**
  - Provide insights into task estimations and technical dependencies.
  - Ensure tasks are actionable and well-defined.
  
- **Testers/QA:**
  - Ensure that tasks have clear acceptance criteria.
  - Identify potential testing requirements early.

---

### Process Steps

1. **Preparation:**
   - **PO:** Prepares a list of candidate **Milestones**, and **Epics** for review.
   - **Architects, Designers, and Engineering Manager:** Review the prepared items for initial feasibility and alignment.
   - **Architects, Designers, and Engineering Manager:** Break down milestones into high-level epics, ensuring scope and alignment with defined milestones.
   
2. **Backlog Grooming Meeting:**
   - **Participants:** PO, Architects, Designers, Engineering Manager, selected Developers, and Testers/QA as needed.
   - **Agenda:**
     - **Review Milestones:** Ensure each milestone has clear objectives and associated epics.
     - **Review Epics:** Review epics to ensure alignment of scope with the milestone.
     - **Review Tasks:** Review tasks, ensuring clarity and feasibility.
     - **New Epics / Tasks** Identify missing epics and tasks to fulfil the requirements of milestones and epics, definition of any areas identified to be done outside of the grooming meeting.
     - **Prioritization:** Order backlog items based on priority, dependencies, and team capacity.
     - **Validation:** Confirm that each item meets the defined criteria for progression.
   
3. **Validation and Criteria Checking:**
   - **Milestones:**
     - **Reviewed By:** PO, Architects, Engineering Manager
     - **Criteria:**
       - Clear objective and alignment with product goals.
       - Feasibility assessed by key stakeholders.
   
   - **Epics:**
     - **Reviewed By:** Architects, Designers, PO, Engineering Manager
     - **Criteria:**
       - High-level breakdown and scope definition.
       - Alignment with associated milestone.
       - Initial feasibility assessment.
   
   - **Tasks:**
     - **Reviewed By:** Architects, Designers, PO, Engineering Manager, Developers, Testers/QA, SRE
     - **Criteria:**
       - Specific and actionable with clear acceptance criteria.
       - Assigned ownership and estimated effort.
       - Dependencies identified and documented.
   
4. **Finalization:**
   - **Engineering Manager:** Confirms that all reviewed items meet the criteria.
   - **PO:** Updates the backlog with refined and prioritized items.
   - **Team:** Ensures that everyone is aligned with the upcoming work and understands their responsibilities.

---

### Progression Criteria

Each backlog item must meet specific criteria before advancing to the next stage. This ensures clarity, alignment, and feasibility throughout the project lifecycle.

Only Epics and Tasks that meet all criteria should appear in the backlog with a status Ready for Development, only these tasks should make it into any sprint.

#### Milestone to Epic

| **Criteria**                  | **Description**                                                                 |
|-------------------------------|---------------------------------------------------------------------------------|
| Clear Objective               | The milestone defines a significant and achievable goal.                       |
| Alignment with Product Goals  | The milestone supports the overall vision and objectives of the product.       |
| Feasibility                   | The milestone is practical within the given timeline and resource constraints.  |

#### Epic to Task

| **Criteria**                  | **Description**                                                                 |
|-------------------------------|---------------------------------------------------------------------------------|
| High-Level Breakdown          | The epic is broken down into meaningful, manageable components.                |
| Scope Definition              | The epic has clearly defined boundaries and objectives.                       |
| Alignment with Milestone      | Each epic directly contributes to the achievement of the milestone.             |
| Initial Feasibility Assessment | The epic is actionable and aligns with architectural and design standards.      |

#### Task Readiness

| **Criteria**                  | **Description**                                                                 |
|-------------------------------|---------------------------------------------------------------------------------|
| Specific and Actionable       | The task has a clear, defined action to be completed.                          |
| Acceptance Criteria           | Specific conditions that must be met for task completion are defined.          |
| Estimation                    | The effort required to complete the task is estimated.                         |
| Dependencies Identified       | Any dependencies on other tasks or external factors are noted.                 |
