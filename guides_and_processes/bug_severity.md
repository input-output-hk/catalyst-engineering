# Bugs Severity

- [Bugs Severity](#bugs-severity)
  - [Purpose](#purpose)
  - [Scope](#scope)
  - [Urgent](#urgent)
  - [High](#high)
  - [Medium](#medium)
  - [Low](#low)

## Purpose

This policy outlines the guidelines for classifying the severity of bugs found by the Catalyst Team

## Scope

This policy applies to all members of the Catalyst Engineering team involved in the development and maintenance.

## Critical

A **critical bug** is a defect in a software application that causes a complete failure or breakdown of the system, significantly affecting its core functionality, security, or stability. Critical bugs typically require immediate attention and resolution because they can lead to severe consequences, such as system crashes, data loss, or serious security vulnerabilities. These bugs are often prioritized above all others due to their potential to disrupt operations, damage user trust, or even result in legal or financial repercussions.

Examples of critical bugs include:

1. **System crashes or hangs** – Bugs that cause the application or the entire system to crash, freeze, or become unresponsive, making it completely unusable for the end user.
2. **Data corruption or loss** – Bugs that lead to the loss or corruption of important data, such as user information, transactions, or files, can result in serious consequences for both the user and the organization.
3. **Security vulnerabilities** – Bugs that expose the application or system to attacks, such as SQL injection, cross-site scripting (XSS), or unauthorized access, which could compromise sensitive data or lead to a breach.
4. **Inability to perform critical functions** – A bug that disables core functions of the software, such as a payment processing system failing during a transaction, or login functionality being broken, prevents users from completing vital actions.

Because of their potential to disrupt business operations, compromise user security, or cause significant harm, critical bugs are addressed immediately, often halting other work or features until the issue is resolved.

## High

A **high-priority bug** is an issue that significantly affects the functionality, usability, or performance of a system but does not necessarily cause a complete failure. These bugs are often critical to address quickly because they impact important features or workflows, leading to potential disruptions for users or customers. While not as severe as critical bugs (which may cause system crashes or security vulnerabilities), high-priority bugs can still result in major user dissatisfaction, loss of productivity, or even financial consequences.

Examples of high-priority bugs include:

1. **Key features that are broken** – When a core feature, such as a payment gateway, user authentication, or data retrieval, is not working properly, it can prevent users from completing tasks and cause significant interruptions to service.
2. **Performance degradation** – A bug that causes slow response times or lag, particularly in critical workflows, can make the system unusable for users, even if it doesn’t cause a full crash.
3. **Data inconsistencies or errors** – Bugs that cause inaccurate data to be displayed or processed, especially in business-critical applications, can undermine trust and lead to poor decision-making.
4. **Cross-platform issues** – Bugs that impact how a system behaves on certain devices or browsers, especially if the system is intended to work across a wide range of platforms, can prevent a significant portion of users from accessing the service properly.

In general, high-priority bugs need to be resolved swiftly, as their impact is noticeable enough to affect the user experience or system reliability, but they don’t warrant immediate emergency attention like a critical bug would.

## Medium

A **medium-severity bug** is an issue that affects the functionality or usability of a system but does not cause a critical failure or severely disrupt the user experience. While not as urgent as high or critical bugs, medium bugs still need to be addressed in a reasonable time frame because they can impact user satisfaction, system performance, or the flow of certain tasks. These bugs are usually non-fatal and don't stop the user from completing essential actions, but they may cause inconvenience, inconsistency, or minor disruptions.

Examples of medium-severity bugs include:

1. **Minor UI/UX issues** – Problems like misaligned elements, broken links, or confusing navigation that affect the aesthetic or ease of use but don’t prevent users from using the software effectively.
2. **Partial functionality failures** – Features that don’t work as expected but still allow the user to continue interacting with the system (for example, a search function that returns incorrect results but doesn’t prevent the user from browsing the application).
3. **Performance issues** – Slower load times or performance degradation in certain non-critical areas that don’t render the system unusable but can detract from the overall user experience.
4. **Inconsistent behavior** – Features that work differently in some cases but are still functional, such as a button not responding on one browser but working fine on another.

Medium bugs should be addressed after high and critical bugs, but still within a reasonable timeframe, especially if they impact the overall usability or user satisfaction in a noticeable way. They can often be fixed in regular updates or as part of routine maintenance.

## Low

A **low-severity bug** is an issue in the software that has minimal impact on the functionality or user experience. These bugs are typically cosmetic in nature or involve minor features that don't affect the core operations of the application. While low-severity bugs should still be addressed eventually to maintain overall quality and polish, they do not disrupt the system's main processes or cause significant problems for users.

Examples of low-severity bugs include:

1. **Cosmetic issues** – Minor visual flaws such as incorrect fonts, colors, or alignment problems that don't affect the user’s ability to interact with the software or complete tasks.
2. **Typos or grammatical errors** – Small text mistakes in UI elements, messages, or instructions that may affect professionalism but do not hinder functionality.
3. **Non-critical feature glitches** – Features that behave incorrectly but have little to no effect on the user’s ability to complete important actions (for example, a non-functioning tooltip or a small, non-essential option not displaying correctly).
4. **Minor compatibility issues** – Occasional glitches on specific devices or browsers that don’t affect most users and don’t interfere with key functionality.

Low-severity bugs are typically lower priority and can be addressed during regular maintenance cycles or in future updates. They are usually the last to be fixed, especially if resources are limited and higher-severity bugs are present.
