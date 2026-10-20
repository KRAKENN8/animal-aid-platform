# Software Requirements Specification (SRS)
# Animal Aid Platform

## Document Information

| Field | Value |
|---|---|
| Project Name | Animal Aid Platform |
| Document Version | 0.1 |
| Status | Draft |
| Created | 19-10-2026 |
| Last Updated | 20-10-2026 |
| Author / Reviewer / Approver | [Ivan Petrov](https://github.com/KRAKENN8), [Maksim Koroljov](https://github.com/rewazi) |

---

# 1. Introduction

## 1.1 Purpose

This document defines the software requirements for Animal Aid Platform. It establishes the expected system behavior, functional and non-functional requirements, constraints, and acceptance criteria.

The document serves as a reference for project planning, design, implementation, testing, and evaluation. It will be updated as requirements become more precise and decisions are confirmed.

## 1.2 Project Purpose

The purpose of Animal Aid Platform is to centralize information about animals in need of homes and improve coordination between animal shelters, volunteers, and people willing to help.

The platform is intended to provide the following capabilities:

- Aggregating animal adoption listings from multiple animal shelters in a single web application.
- Coordinating activities and assistance between animal shelters and volunteers.
- Managing adoption applications.
- Supporting temporary animal fostering.
- Providing communication between users, shelters, and volunteers.
- Providing an administrative interface for managing platform users and content.

Additional capabilities may be considered for future versions.

## 1.3 Scope

### In Scope

The Minimum Viable Product (MVP) includes:

- A public catalogue of animals available for adoption.
- Animal search and filtering.
- User registration and account management.
- Animal shelter registration and administrator verification.
- Animal listing creation and management by authorized shelter representatives.
- Adoption application submission and processing.
- Communication between adoption applicants and shelters.
- Volunteer profiles and volunteer verification.
- Volunteer assistance requests and tasks.
- Temporary fostering requests and offers.
- Automatic suggestions for the nearest shelter, with the ability to select another shelter.
- Internal messaging and direct contact information.
- User interface in Estonian, Russian, and English.
- In-app and email notifications.
- Administrative management of users, shelters, volunteers, animal listings, and platform statistics.
- Content and account moderation capabilities.

### Out of Scope

The following features are not included in the MVP:

- AI-powered animal matching assistant.
- Public lost-and-found animal announcements with an interactive map.
- Automatic importing of animal listings from external sources.
- Ratings and reviews.

These exclusions apply to the MVP and do not necessarily rule out future development.

## 1.4 Intended Audience

This document is intended for:

- Project developers.
- Project supervisors and evaluators.
- Animal shelters participating in the platform.
- Volunteers and registered users involved in requirements validation.
- Testers responsible for verifying the implemented requirements.

## 1.5 Definitions and Abbreviations

| Term | Definition |
|---|---|
| Animal Aid Platform | The regional web application described in this document. |
| MVP | Minimum Viable Product: the initial version containing the agreed essential functionality. |
| SRS | Software Requirements Specification. |
| Guest | An unauthenticated user who can access public information. |
| Registered User | An authenticated user who can use account-dependent platform features. |
| Shelter Representative | A user authorized to represent an approved animal shelter. |
| Volunteer | A user who offers assistance to animal shelters. |
| Administrator | A user authorized to manage and moderate the platform. |
| Adoption Application | A request submitted by a user to adopt an animal. |
| Fostering | Temporary care of an animal until a longer-term arrangement is available. |
| Help Request | A request for assistance submitted through the platform. |
| Volunteer Task | A defined activity created to coordinate assistance. |

## 1.6 References

| Reference | Description |
|---|---|
| Project SRS | This document. |
| Applicable legislation | Relevant Estonian and European Union requirements concerning personal data and privacy; specific legal requirements remain to be verified. |
| Technical documentation | To be added after the technology stack and external services are selected. |

---

# 2. Overall Description

## 2.1 Product Perspective

Animal Aid Platform is a regional web application intended to connect animal shelters, people interested in adoption, and volunteers.

The system will provide a shared interface for viewing animal listings, submitting adoption applications, organizing volunteer assistance, coordinating temporary fostering, and communicating between participants.

The platform will include separate permissions for guests, registered users, shelter representatives, volunteers, and administrators.

The application is intended to serve the Ida-Viru County region of Estonia initially.

The final architecture, technology stack, hosting environment, and external service providers have not yet been specified in this document.

## 2.2 Product Objectives

The primary objectives are:

- Centralize animal adoption information from participating shelters.
- Make animal listings easier to discover and compare.
- Simplify communication between potential adopters and shelters.
- Improve coordination of volunteer assistance.
- Provide a structured process for shelter registration and verification.
- Support temporary fostering arrangements.
- Reduce the need to coordinate platform-related activities through separate communication channels.
- Provide administrators with tools to manage accounts, content, and platform activity.
- Support Estonian, Russian, and English interfaces.

## 2.3 Stakeholders

| Stakeholder | Interest |
|---|---|
| Project developers | Implementing, testing, and maintaining the application. |
| Project supervisor | Reviewing project progress and deliverables. |
| Animal shelters | Managing animal listings, reviewing adoption applications, and requesting assistance. |
| Potential adopters | Finding animals and communicating with shelters. |
| Volunteers | Offering assistance and responding to tasks. |
| Platform administrators | Managing accounts, verifying participants, moderating content, and monitoring activity. |
| Animals in need | Indirect beneficiaries of improved adoption and assistance coordination. |

## 2.4 User Classes and Characteristics

| User Class | Description | Main Needs |
|---|---|---|
| Guest | An unauthenticated visitor. | Browse public animal listings and public information. |
| Registered User | An authenticated platform user. | Manage a profile, submit adoption applications, communicate with shelters, and receive notifications. |
| Animal Shelter Representative | A representative of an approved shelter. | Manage the shelter's animal listings, process applications, communicate with users, and coordinate assistance. |
| Volunteer | A user who offers help to shelters. | Maintain a volunteer profile, offer assistance, respond to tasks, and coordinate activities. |
| Platform Administrator | A user with administrative permissions. | Manage users, verify shelters and volunteers, manage listings, review moderation matters, and view platform statistics. |

## 2.5 Operating Environment

The system will be a web application intended to be accessible through a web browser.

The initial target region is Ida-Viru County, Estonia.

The application must support three interface languages:

- Estonian.
- Russian.
- English.

The exact supported browsers, minimum screen sizes, hosting environment, and deployment requirements remain to be specified.

## 2.6 Assumptions and Dependencies

### Assumptions

- Participating animal shelters will provide accurate information about their animals.
- Shelter representatives will be responsible for updating listing information and confirming completed adoptions.
- Users will provide contact information necessary for platform communication.
- Volunteers will provide accurate information about their availability and the assistance they can offer.
- Users will have access to an internet connection and a supported web browser.
- The platform will initially focus on Ida-Viru County.

### Dependencies

- An email delivery service will be required for email notifications.
- A method for determining or calculating geographic distance will be required to suggest nearby shelters.
- Browser geolocation may be used when the user grants permission.
- Manual location entry must be supported.
- External service providers and their final integration methods remain to be selected.

## 2.7 Constraints

- The MVP must remain within the agreed project scope.
- The interface must support Estonian, Russian, and English.
- Only approved shelter representatives may manage their shelter's listings.
- Administrative permissions must be separated from ordinary user permissions.
- The system must not assume that an adoption has been completed merely because an application has been approved.
- Personal data must be handled in accordance with applicable requirements.
- The technology stack, hosting budget, and specific infrastructure constraints have not yet been confirmed.

## 2.8 Risks

| Risk ID | Risk | Potential Impact | Mitigation |
|---|---|---|---|
| RISK-001 | Incorrect or outdated animal information | Users may receive misleading information. | Allow authorized shelters to update listings and confirm adoption completion. |
| RISK-002 | Unauthorized shelter registrations | Untrusted users may publish misleading listings. | Require administrator verification before granting shelter management permissions. |
| RISK-003 | Abuse of volunteer functionality | Tasks or assistance requests may be misused. | Provide administrative account management and appropriate moderation controls. |
| RISK-004 | Email delivery failures | Users may miss important notifications. | Handle delivery errors and provide in-app notifications for supported events. |
| RISK-005 | Inaccurate location data | The suggested shelter may not be the most suitable one. | Allow manual location entry and manual shelter selection. |
| RISK-006 | Unclear workflow rules | Different participants may interpret statuses differently. | Define and validate status transitions before implementation is finalized. |
| RISK-007 | Exposure of personal information | Privacy violations or misuse of contact details. | Define access permissions and data-handling rules before implementation. |

---

# 3. Functional Requirements

## 3.1 Functional Areas

The MVP consists of the following functional areas:

1. Animal Adoption Catalogue.
2. User Registration and Account Management.
3. Animal Shelter Registration and Verification.
4. Animal Listing Management.
5. Adoption Application Management.
6. User and Shelter Communication.
7. Volunteer Profile Management and Verification.
8. Volunteer Assistance Requests and Tasks.
9. Temporary Animal Fostering.
10. Location-Based Shelter Suggestions.
11. Multilingual Interface.
12. Notifications.
13. Platform Administration and Moderation.
14. Platform Statistics.

AI-powered matching, public lost-and-found announcements with an interactive map, and external listing imports are excluded from the MVP.

## 3.2 Functional Requirements

The requirements below describe the agreed functionality at a preliminary level. Priorities, validation rules, and detailed status transitions must be reviewed during subsequent refinement.

### FR-001 — Browse and Search Animal Listings

**Description**

The system shall allow users to browse published animal listings and filter them by animal species, age, sex, size, shelter, characteristics, and health condition.

Users shall be able to search listing descriptions and view animal photographs.

**Priority:** High

**Preconditions:**
- The catalogue is accessible.
- Published listings are available, if any exist.

**Main Flow:**
1. The user opens the animal catalogue.
2. The system displays available published listings.
3. The user optionally enters search terms or selects filters.
4. The system displays matching listings.
5. The user opens a listing to view its details.

**Alternative Flows:**
- The user browses without applying filters.
- No listings match the selected filters; the system displays an empty result and allows the user to change the search criteria.

**Error Handling:**
- Invalid search or filter input is handled without breaking the catalogue.
- A listing that is no longer available is not presented as available for adoption.

**Acceptance Criteria:**
- Guests can browse public listings.
- Users can apply the supported filters.
- Users can view listing descriptions and photographs.
- Empty search results are handled clearly.

### FR-002 — Animal Listing Management

**Description**

The system shall allow authorized representatives of approved shelters to create and manage their shelter's animal listings.

Administrators shall be able to create, edit, and delete listings across shelters.

A listing may contain:

- Animal name.
- Species.
- Breed.
- Age or date of birth.
- Sex.
- Size.
- Personality and behavioural characteristics.
- Description.
- Health condition.
- Vaccination status.
- Sterilization status.
- Special care requirements.
- Photographs.
- Shelter contact information.

The system shall support unknown or unavailable animal information where applicable, subject to the final field-validation rules.

**Priority:** High

**Preconditions:**
- A shelter representative belongs to an approved shelter, or the user has administrative permissions.

**Main Flow:**
1. The authorized user opens listing management.
2. The user creates or selects a listing.
3. The user enters or updates the available information.
4. The system validates the submitted data.
5. The system saves the listing.
6. The listing is published or updated according to its status.

**Alternative Flows:**
- The user edits an existing listing.
- An administrator modifies a listing on behalf of a shelter.
- The user saves a listing with optional information unavailable, where permitted.

**Error Handling:**
- Invalid required fields are identified.
- Unauthorized users cannot modify the listing.
- Invalid or unsupported photograph uploads are rejected.

**Acceptance Criteria:**
- Approved shelters can manage their own listings.
- Shelter representatives cannot manage another shelter's listings unless separately authorized.
- Administrators can manage listings across shelters.
- Listings support the defined animal information and photographs.
- A listing is not marked as adopted until the shelter confirms that the adoption has actually taken place.

### FR-003 — Shelter Registration and Verification

**Description**

The system shall allow a prospective shelter representative to submit a shelter registration request.

The request shall include shelter information and supporting evidence.

**Priority:** High

**Preconditions:**
- The registration interface is accessible.
- The applicant can provide the requested information.

**Main Flow:**
1. The applicant opens the shelter registration form.
2. The applicant enters shelter and representative information.
3. The applicant submits the registration request.
4. The system validates the submission.
5. The system records the request for administrator review.
6. The administrator reviews the request.
7. The administrator approves or rejects the request.
8. The system informs the applicant of the decision.

**Alternative Flows:**
- The administrator requests additional information.
- The administrator rejects the request with a reason.
- The applicant corrects the information and resubmits the request.

**Error Handling:**
- Missing or invalid required information is identified.
- An unapproved shelter cannot manage animal listings.

**Acceptance Criteria:**
- Applicants can submit shelter registration requests.
- Administrators can review, approve, and reject requests.
- Applicants can see the decision and rejection reason.
- Rejected applicants can correct their information and resubmit.
- Only approved shelters receive shelter management permissions.

**Registration information:**
- Shelter name.
- Address and location.
- Telephone number.
- Email address.
- Description of activities.
- Representative's name and contact information.
- Supporting documents or an official website link.

A potential shelter registration option should be clearly presented during registration rather than discovered accidentally. Email-domain analysis may be used as part of the registration approach, but the exact decision rules and verification procedure remain to be finalized.

### FR-004 — User Registration and Account Management

**Description**

The system shall allow ordinary users to register without paying a registration fee and manage their account information.

Email verification is not mandatory for ordinary platform use in the MVP.

**Priority:** High

**Preconditions:**
- The registration interface is available.

**Main Flow:**
1. The user opens the registration form.
2. The user provides the required account information.
3. The system validates the information.
4. The system creates the account.
5. The user can sign in and access account-dependent features.

**Alternative Flows:**
- The user edits personal information.
- The user changes the preferred interface language.
- The user signs out.

**Error Handling:**
- Invalid or incomplete required information is rejected.
- Duplicate account identifiers are handled according to the final account rules.
- Authentication failures do not grant access to protected features.

**Acceptance Criteria:**
- Ordinary users can register without payment.
- Users can sign in and manage their profiles.
- Email verification is not a general prerequisite for ordinary platform use.
- Protected features require the appropriate account permissions.

### FR-005 — Adoption Application Management

**Description**

The system shall allow a registered user to submit adoption applications for animal listings.

A user may submit applications for multiple animals simultaneously.

Shelter representatives shall be able to review applications concerning their shelter's animals and communicate with applicants.

**Priority:** High

**Preconditions:**
- The user is authenticated.
- The listing accepts adoption applications.

**Main Flow:**
1. The user opens an animal listing.
2. The user submits an adoption application.
3. The system records the application.
4. The relevant shelter receives the application.
5. The shelter reviews the application.
6. The shelter updates the application status.
7. The user can view the status and communicate with the shelter.
8. The shelter confirms the actual adoption when it takes place.
9. The listing is updated to reflect the completed adoption.

**Alternative Flows:**
- The shelter requests additional information.
- The shelter declines the application.
- The user has applications for multiple animals at the same time.

**Error Handling:**
- Applications cannot be submitted for listings that no longer accept applications.
- Users cannot access another user's private application information.
- Unauthorized users cannot process applications.

**Acceptance Criteria:**
- Registered users can submit applications.
- Users can have multiple applications at the same time.
- Authorized shelter representatives can review applications.
- Applicants can communicate with the shelter.
- Application approval alone does not mark the animal as adopted.
- The shelter must confirm actual adoption completion before the listing is marked as adopted.

The final application statuses and all allowed status transitions remain to be defined.

### FR-006 — User Profile and Application Overview

**Description**

The system shall allow registered users to view and update their personal profiles, review their adoption applications, access application statuses, view message history, manage contact information, and select an interface language.

**Priority:** High

**Preconditions:**
- The user is authenticated.

**Main Flow:**
1. The user opens the profile.
2. The system displays the user's permitted profile information.
3. The user updates editable fields or opens their applications.
4. The system validates and saves changes.

**Alternative Flows:**
- The user changes the interface language.
- The user opens a previous conversation.

**Error Handling:**
- Invalid profile data is rejected.
- A user cannot modify another user's profile.

**Acceptance Criteria:**
- Users can view and edit their permitted profile information.
- Users can view their adoption applications and statuses.
- Users can access their own message history.
- Users can manage contact information and language preferences.

### FR-007 — Volunteer Profile Management and Verification

**Description**

The system shall allow users to create and update volunteer profiles.

A volunteer profile shall include:

- First and last name.
- Email address.
- Telephone number.
- Location.
- Types of assistance offered.
- Availability.
- Experience with animals.
- Additional information.

Volunteer verification may be performed by an administrator or an authorized shelter. The exact scope of shelter approval must be clarified.

**Priority:** High

**Preconditions:**
- The user has an account.

**Main Flow:**
1. The user opens the volunteer registration form.
2. The user provides the required profile information.
3. The system validates and saves the profile.
4. The profile is submitted for verification.
5. An authorized administrator or shelter reviews the profile.
6. The verification decision is recorded.
7. The user is informed of the decision.

**Alternative Flows:**
- The reviewer rejects the profile or requests additional information.
- The user updates the profile and resubmits it.

**Error Handling:**
- Missing or invalid required fields are identified.
- Unverified volunteers cannot perform actions restricted to verified volunteers.

**Acceptance Criteria:**
- Users can create and update volunteer profiles.
- The defined profile fields are supported.
- Authorized reviewers can approve or reject volunteer profiles.
- The system enforces the permissions associated with the resulting verification status.

### FR-008 — Volunteer Assistance Requests

**Description**

The system shall allow registered users and volunteers to submit assistance requests to an animal shelter.

The system shall suggest a nearby shelter based on the available location information. The user shall be able to select another shelter manually.

**Priority:** High

**Preconditions:**
- The user is authenticated.
- At least one shelter is available to receive requests.

**Main Flow:**
1. The user opens the assistance request interface.
2. The user provides the request details and location.
3. The system suggests a nearby shelter.
4. The user confirms the suggested shelter or selects another one.
5. The system records the request and makes it available to the selected shelter.
6. The shelter responds through the platform.

**Alternative Flows:**
- The user enters a location manually.
- The user grants permission for browser geolocation.
- The user selects a shelter different from the suggested one.

**Error Handling:**
- If location information is unavailable, the user can enter it manually.
- If a nearby shelter cannot be determined, the system allows manual shelter selection.
- The system does not assume that the suggested shelter is necessarily the most suitable one.

**Acceptance Criteria:**
- Users can submit assistance requests.
- The system supports browser geolocation and manual location entry.
- The system suggests a nearby shelter when sufficient location data is available.
- Users can select another shelter.
- The selected shelter can receive and respond to the request.

### FR-009 — Volunteer Task Management

**Description**

The system shall allow shelters to create volunteer tasks and allow volunteers to respond to available tasks.

Supported assistance categories include:

- Transporting animals.
- Providing food, medicine, and other necessary supplies.
- Walking, caring for, and socializing animals.
- Participating in shelter events.
- Assisting with searches for lost animals, subject to the final definition of how such searches are coordinated within the MVP.

**Priority:** High

**Preconditions:**
- A shelter representative is authorized to create tasks.
- A volunteer has the permissions required to respond to tasks.

**Main Flow:**
1. A shelter representative creates a task and provides its details.
2. The system publishes the task to eligible users.
3. A volunteer responds to the task.
4. The shelter reviews the responses.
5. The shelter selects an executor.
6. The task progresses through its defined lifecycle.
7. The responsible participants record completion.

**Alternative Flows:**
- A volunteer declines or withdraws a response.
- A task is cancelled.
- A shelter updates task details.

**Error Handling:**
- Unauthorized users cannot create or modify shelter tasks.
- Invalid task data is rejected.
- Responses to unavailable tasks are not accepted.

**Acceptance Criteria:**
- Authorized shelters can create and manage tasks.
- Volunteers can view and respond to eligible tasks.
- Shelters can select a volunteer to perform a task.
- Task status and lifecycle rules are enforced.

The complete task statuses, cancellation permissions, and handling of unsuccessful responses remain to be defined.

### FR-010 — Temporary Animal Fostering

**Description**

The system shall support temporary fostering through both shelter requests and volunteer offers.

**Priority:** High

**Preconditions:**
- The relevant shelter or volunteer is authorized to use fostering functionality.

**Main Flow:**
1. A shelter publishes a temporary fostering request, or a volunteer publishes an offer to provide temporary care.
2. The system makes the request or offer available to relevant participants.
3. Interested participants respond.
4. The shelter and volunteer coordinate through the platform.
5. The participants agree on the arrangement.
6. The arrangement is updated when it is completed or cancelled.

**Alternative Flows:**
- A volunteer is unavailable.
- A shelter withdraws a request.
- Participants do not reach an agreement.

**Error Handling:**
- Unauthorized users cannot modify another participant's requests or offers.
- Invalid or incomplete required information is rejected.

**Acceptance Criteria:**
- Shelters can publish fostering requests.
- Volunteers can publish fostering offers.
- Interested participants can respond and communicate.
- The system records the arrangement according to the finalized fostering workflow.

The exact matching, approval, and completion rules remain to be defined.

### FR-011 — Internal Messaging and Contact Information

**Description**

The system shall provide internal messaging and support the display of relevant direct contact information.

Internal communication shall support at least:
- Adoption applicants communicating with the relevant shelter.
- Shelters and volunteers coordinating assistance and tasks.

**Priority:** High

**Preconditions:**
- The user is authorized to participate in the relevant interaction.

**Main Flow:**
1. A user opens an authorized conversation or contact section.
2. The user sends a message or views the permitted contact details.
3. The system records the message and makes it available to authorized participants.
4. Participants can review the conversation history.

**Alternative Flows:**
- A participant returns to an existing conversation.
- A user receives a notification about a new message.

**Error Handling:**
- Unauthorized users cannot access private conversations.
- Failed message submissions are reported to the sender.
- The system must not expose private contact details outside the applicable permissions.

**Acceptance Criteria:**
- Authorized participants can exchange messages.
- Message history is available to the relevant participants.
- Relevant direct contact information can be displayed.
- Access to conversations and contact information is restricted appropriately.

### FR-012 — Multilingual Interface

**Description**

The system shall provide an interface in Estonian, Russian, and English.

The system shall initially attempt to determine the preferred language from the browser or device language settings. Users shall be able to change the language manually.

**Priority:** High

**Preconditions:**
- The application is accessible.

**Main Flow:**
1. The user opens the application.
2. The system selects an initial language based on browser or device settings when supported.
3. The user can select another supported language.
4. The system displays the interface in the selected language.
5. The selected language is retained for subsequent visits according to the finalized preference-storage rules.

**Alternative Flows:**
- The detected language is unsupported; the system uses a defined fallback language.
- The user changes the language manually.

**Error Handling:**
- Missing translations must not prevent core functionality from working.

**Acceptance Criteria:**
- Estonian, Russian, and English are supported.
- Users can switch languages manually.
- The system can choose an initial language based on browser or device settings.
- Language preference is retained between visits.

The fallback language and the exact mechanism for storing the preference remain to be confirmed.

### FR-013 — Notifications

**Description**

The system shall provide in-app and email notifications for supported events.

Confirmed notification events include:
- Adoption application status changes.
- New messages.
- Shelter registration status changes.
- Requests for additional information during shelter verification.

**Priority:** High

**Preconditions:**
- The relevant event occurs.
- The recipient is eligible to receive the notification.

**Main Flow:**
1. A supported event occurs.
2. The system determines the relevant recipient.
3. The system creates an in-app notification.
4. The system attempts to send an email notification where applicable.
5. The user can access the notification and relevant information.

**Alternative Flows:**
- An email cannot be delivered.
- The user reads an in-app notification later.

**Error Handling:**
- Email delivery failure must not prevent the system from retaining relevant in-app information.
- Notification failures must be handled without corrupting the underlying application or message data.

**Acceptance Criteria:**
- In-app notifications are available for supported events.
- Email notifications are attempted for supported events.
- Users can access relevant notifications.
- The notification system handles email delivery failures.

Other notification events, notification preferences, and retention rules remain to be defined.

### FR-014 — Platform Administration

**Description**

The system shall provide administrators with functionality to:

- View and manage user accounts.
- Approve and reject shelter registration requests.
- Verify volunteers.
- Create, edit, and delete animal listings across shelters.
- Manage and moderate platform content.
- Block and unblock accounts.
- View assistance requests and volunteer tasks.
- View basic platform statistics, including counts of users, shelters, animals, and adoption applications.

**Priority:** High

**Preconditions:**
- The user is authenticated and has administrative permissions.

**Main Flow:**
1. The administrator opens the administrative interface.
2. The system displays the functions permitted to the administrator.
3. The administrator selects a management operation.
4. The system validates the operation and permissions.
5. The system records the permitted changes.

**Alternative Flows:**
- The administrator reviews a registration request.
- The administrator blocks or unblocks an account.
- The administrator views platform statistics.

**Error Handling:**
- Non-administrators cannot access administrative functions.
- Invalid operations are rejected.
- Failed changes are reported without incorrectly indicating success.

**Acceptance Criteria:**
- Administrators can perform the listed management operations.
- Administrative permissions are enforced.
- Account and content changes are reflected in the system.
- The administrator can view the specified basic statistics.

### FR-015 — Content and Account Moderation

**Description**

The system shall provide administrative capabilities for reviewing and moderating platform content and accounts.

The exact complaint-submission and complaint-processing policy requires confirmation. The current requirements discussion contains an unresolved inconsistency regarding whether users will be able to submit complaints.

**Priority:** Medium — preliminary

**Preconditions:**
- The administrator is authenticated.
- The relevant moderation functionality is enabled.

**Main Flow:**
1. The administrator opens the moderation interface.
2. The system displays the content or account information the administrator is authorized to review.
3. The administrator examines the information.
4. The administrator performs an authorized moderation action.
5. The system records the resulting change.

**Alternative Flows:**
- The administrator takes no action.
- The administrator blocks an account or modifies/removes content, where authorized.

**Error Handling:**
- Unauthorized users cannot perform moderation actions.
- Invalid moderation operations are rejected.

**Acceptance Criteria:**
- Administrators can access the moderation functions permitted by their role.
- Moderation actions are enforced by the system.
- The complaint-specific workflow is finalized before complaint functionality is considered complete.

### FR-016 — Platform Statistics

**Description**

The system shall allow administrators to view basic platform statistics.

**Priority:** Medium — preliminary

**Preconditions:**
- The administrator is authenticated.

**Main Flow:**
1. The administrator opens the statistics section.
2. The system retrieves the available aggregate counts.
3. The system displays counts of users, shelters, animals, and adoption applications.

**Error Handling:**
- Statistics cannot be retrieved; the system reports that the information is unavailable.

**Acceptance Criteria:**
- Administrators can access the defined statistics.
- The displayed values are derived from the available platform data.

---

# 4. User Roles and Access Control

## 4.1 User Roles

| Role ID | Role Name | Description |
|---|---|---|
| ROLE-001 | Guest | An unauthenticated user who can browse public animal listings and information. |
| ROLE-002 | Registered User | An authenticated user who can manage a profile, submit adoption applications, communicate with shelters, and request assistance. |
| ROLE-003 | Animal Shelter Representative | A representative of an approved shelter who can manage the shelter's listings, process applications, and coordinate assistance. |
| ROLE-004 | Volunteer | A user who offers assistance and can participate in eligible tasks and fostering arrangements, subject to applicable verification rules. |
| ROLE-005 | Platform Administrator | A user authorized to manage accounts, verify shelters and volunteers, manage listings, moderate content, and view platform statistics. |

## 4.2 Permissions

The following matrix is preliminary. Exact permissions must be validated during implementation planning.

| Action | Guest | Registered User | Shelter Representative | Volunteer | Administrator |
|---|---|---|---|---|---|
| Browse public animal listings | Yes | Yes | Yes | Yes | Yes |
| Manage personal profile | No | Yes | Yes | Yes | Yes |
| Submit adoption application | No | Yes | Yes, as a user | Yes, as a user | Yes, as a user |
| View own adoption applications | No | Yes | Yes | Yes | Yes |
| Review applications for own shelter | No | No | Yes | No | Yes |
| Create/manage own shelter's listings | No | No | Yes | No | Yes |
| Manage listings across shelters | No | No | No | No | Yes |
| Submit shelter registration | Not yet authorized | Yes | Existing status applies | Existing status applies | Administrative control |
| Verify shelter registrations | No | No | No | No | Yes |
| Create/update volunteer profile | No | Yes | Yes | Yes | Yes |
| Verify volunteer profile | No | No | Subject to approval rules | No | Yes |
| Submit assistance request | No | Yes | Yes | Yes | Yes |
| Create shelter volunteer task | No | No | Yes | No | Yes |
| Respond to eligible volunteer task | No | Subject to eligibility rules | Subject to eligibility rules | Yes | Administrative control |
| Use internal messaging | No | Yes, when authorized | Yes, when authorized | Yes, when authorized | According to administrative permissions |
| Block/unblock accounts | No | No | No | No | Yes |
| View platform statistics | No | No | No | No | Yes |

The matrix does not grant administrative access to private messages by default. Any such access must be explicitly defined and justified.

## 4.3 Authentication Requirements

- Account-dependent functionality shall require authentication.
- Public animal listings shall be accessible without authentication.
- The system shall distinguish authenticated users from guests.
- Administrative functions shall require an authenticated account with the administrator role.
- Shelter management functionality shall require an approved shelter and an authorized representative.
- Volunteer functionality shall enforce the applicable volunteer verification rules.
- Email verification shall not be mandatory for ordinary user registration in the MVP.

The authentication method, password policy, account recovery process, and session-management rules remain to be specified.

## 4.4 Authorization Requirements

- Users shall only modify data for which they have permission.
- Shelter representatives shall manage listings belonging to their own shelter.
- Administrators shall be able to manage listings across shelters.
- Users shall only access their own private profile and adoption application data, except where another role has an explicitly defined operational permission.
- Shelter representatives shall only review applications relevant to their shelter.
- Volunteer task actions shall be restricted according to the user's role and verification status.
- Administrative actions shall be protected from non-administrative users.
- Access to messages and contact information shall be limited to authorized participants and explicitly authorized administrative functions.

---

# 5. Use Cases

## UC-001 — Browse Animal Catalogue

**Primary Actor:** Guest or Registered User

**Goal:** Find animals available for adoption.

**Preconditions:** The application is accessible.

**Trigger:** The user opens the animal catalogue.

**Main Success Scenario:**
1. The user opens the catalogue.
2. The system displays published animal listings.
3. The user searches or applies filters.
4. The system displays matching results.
5. The user opens a listing.

**Alternative Scenarios:**
- No matching listings are found.
- The user browses without filters.

**Failure Conditions:**
- The catalogue cannot be loaded.

**Postconditions:** The user has viewed the available listing information.

**Related Requirements:** FR-001, FR-002.

## UC-002 — Submit Adoption Application

**Primary Actor:** Registered User

**Goal:** Apply to adopt an animal.

**Preconditions:** The user is authenticated and the listing accepts applications.

**Trigger:** The user selects the adoption application action.

**Main Success Scenario:**
1. The user opens the animal listing.
2. The user completes and submits the application.
3. The system validates and stores the application.
4. The shelter receives the application.
5. The shelter reviews it.
6. The user can view the application status and communicate with the shelter.

**Alternative Scenarios:**
- The user has other active applications.
- The shelter requests additional information.
- The shelter declines the application.

**Failure Conditions:**
- The listing is no longer accepting applications.
- Required application data is invalid.

**Postconditions:** The application is recorded and available to authorized participants.

**Related Requirements:** FR-005, FR-006, FR-011, FR-013.

## UC-003 — Register and Verify a Shelter

**Primary Actor:** Prospective Shelter Representative

**Goal:** Obtain authorization to manage a shelter's listings.

**Preconditions:** The applicant can access the registration interface.

**Trigger:** The applicant starts shelter registration.

**Main Success Scenario:**
1. The applicant provides shelter and representative information.
2. The system validates the submission.
3. The request is submitted for review.
4. The administrator examines the information.
5. The administrator approves the request.
6. The applicant is notified.
7. The representative receives the applicable shelter permissions.

**Alternative Scenarios:**
- The administrator requests additional information.
- The administrator rejects the request.
- The applicant corrects the information and resubmits it.

**Failure Conditions:**
- Required registration information is invalid.
- The request cannot be saved.

**Postconditions:** The shelter is either approved, rejected, or awaiting further information.

**Related Requirements:** FR-003, FR-013, FR-014.

## UC-004 — Create or Update Animal Listing

**Primary Actor:** Approved Shelter Representative

**Goal:** Publish or update animal information.

**Preconditions:** The representative is authorized to manage the relevant shelter.

**Trigger:** The representative opens listing management.

**Main Success Scenario:**
1. The representative creates a listing or selects an existing one.
2. The representative enters or updates the information.
3. The system validates the data.
4. The system saves the listing.
5. The listing is published or updated according to its status.

**Alternative Scenarios:**
- An administrator modifies the listing.
- Some optional animal information is unavailable.

**Failure Conditions:**
- The user lacks the required permissions.
- Required data is invalid.

**Postconditions:** The listing reflects the saved information.

**Related Requirements:** FR-002, FR-014.

## UC-005 — Register as a Volunteer

**Primary Actor:** Registered User

**Goal:** Offer assistance to animal shelters.

**Preconditions:** The user has an account.

**Trigger:** The user opens volunteer registration.

**Main Success Scenario:**
1. The user enters volunteer profile information.
2. The system validates and saves the profile.
3. The profile is submitted for verification.
4. An authorized administrator or shelter reviews the profile.
5. The system records the decision.
6. The user is informed of the result.

**Alternative Scenarios:**
- Additional information is requested.
- The profile is rejected and later resubmitted.

**Failure Conditions:**
- Required information is invalid.
- The submission cannot be saved.

**Postconditions:** The volunteer profile has a recorded verification state.

**Related Requirements:** FR-007, FR-013, FR-014.

## UC-006 — Submit Assistance Request

**Primary Actor:** Registered User or Volunteer

**Goal:** Request help from an animal shelter.

**Preconditions:** The user is authenticated.

**Trigger:** The user opens the assistance request form.

**Main Success Scenario:**
1. The user describes the assistance needed.
2. The user provides a location.
3. The system suggests a nearby shelter when possible.
4. The user confirms the suggestion or selects another shelter.
5. The system records the request.
6. The shelter receives the request and responds through the platform.

**Alternative Scenarios:**
- The user enters a location manually.
- The user selects a shelter directly.

**Failure Conditions:**
- The request contains invalid required data.
- No shelter can be suggested and the user does not select one.

**Postconditions:** The request is available to the selected shelter.

**Related Requirements:** FR-008, FR-011, FR-013.

## UC-007 — Coordinate a Volunteer Task

**Primary Actor:** Shelter Representative and Volunteer

**Goal:** Organize and complete a volunteer activity.

**Preconditions:** The shelter representative is authorized to create tasks, and the volunteer is eligible to respond.

**Trigger:** A shelter creates a task.

**Main Success Scenario:**
1. The shelter creates and publishes a task.
2. A volunteer views the task.
3. The volunteer responds.
4. The shelter selects an executor.
5. The participants coordinate the activity.
6. The task is updated as the activity progresses.
7. The task is marked complete according to the finalized rules.

**Alternative Scenarios:**
- No volunteer responds.
- A volunteer withdraws.
- The shelter cancels the task.

**Failure Conditions:**
- The task contains invalid information.
- The actor is not authorized to perform the requested action.

**Postconditions:** The task has a recorded outcome.

**Related Requirements:** FR-009, FR-011, FR-013.

## UC-008 — Arrange Temporary Fostering

**Primary Actor:** Shelter Representative or Volunteer

**Goal:** Coordinate temporary care for an animal.

**Preconditions:** The actor is authorized to publish a fostering request or offer.

**Trigger:** A shelter publishes a fostering request or a volunteer publishes an offer.

**Main Success Scenario:**
1. A request or offer is published.
2. An interested participant responds.
3. The participants communicate.
4. The participants agree on the arrangement.
5. The system records the relevant arrangement information.
6. The arrangement is updated when it ends.

**Alternative Scenarios:**
- No suitable participant responds.
- The participants do not reach an agreement.
- The arrangement is cancelled.

**Failure Conditions:**
- The user lacks the necessary permissions.
- Required information is invalid.

**Postconditions:** The fostering request or arrangement has an updated state.

**Related Requirements:** FR-010, FR-011, FR-013.

## UC-009 — Manage Platform

**Primary Actor:** Platform Administrator

**Goal:** Maintain platform integrity and manage users and content.

**Preconditions:** The administrator is authenticated.

**Trigger:** The administrator opens the administrative interface.

**Main Success Scenario:**
1. The administrator selects a management function.
2. The system verifies the administrator's permissions.
3. The administrator reviews the relevant information.
4. The administrator performs an authorized action.
5. The system saves the result.

**Alternative Scenarios:**
- The administrator reviews a shelter registration.
- The administrator verifies a volunteer.
- The administrator blocks an account or modifies a listing.
- The administrator views platform statistics.

**Failure Conditions:**
- The operation is invalid.
- The system cannot save the change.

**Postconditions:** The relevant management operation is recorded.

**Related Requirements:** FR-003, FR-007, FR-014, FR-015, FR-016.

---

# 6. Business Rules

| Rule ID | Rule | Description |
|---|---|---|
| BR-001 | Public Catalogue Access | Animal listings published for public viewing can be browsed without authentication. |
| BR-002 | Shelter Verification | Only approved shelters can manage their animal listings. |
| BR-003 | Listing Ownership | Shelter representatives can manage their own shelter's listings. |
| BR-004 | Administrative Listing Access | Administrators can manage listings across shelters. |
| BR-005 | Adoption Completion | A listing is marked as adopted only after the shelter confirms that the adoption has actually taken place. |
| BR-006 | Multiple Applications | A registered user may apply to adopt multiple animals simultaneously. |
| BR-007 | Ordinary Registration | Ordinary users can register without paying a fee. |
| BR-008 | Email Verification | Email verification is not mandatory for ordinary platform use in the MVP. |
| BR-009 | Volunteer Verification | Volunteer verification can be performed by an administrator or an authorized shelter; the scope of shelter approval remains to be clarified. |
| BR-010 | Shelter Suggestions | The system may suggest a nearby shelter based on available location information, but users can select another shelter manually. |
| BR-011 | Location Input | Users can provide location information through browser geolocation, when permitted, or manual entry. |
| BR-012 | Interface Languages | The application supports Estonian, Russian, and English. |
| BR-013 | Notifications | Supported events generate in-app notifications and, where applicable, email notifications. |
| BR-014 | Ratings and Reviews | Ratings and reviews are excluded from the MVP. |
| BR-015 | External Listing Imports | External animal listing imports are excluded from the MVP. |

---

# 7. Data Requirements

## 7.1 Data Entities

The following entities are expected to be required. The final data model and relationships will be defined during system design.

| Entity | Description | Example Attributes |
|---|---|---|
| User | A platform account. | ID, email, name, contact details, account status, preferred language. |
| Shelter | An animal shelter registered on the platform. | ID, name, address, location, contact details, description, verification status. |
| Shelter Representative | A user associated with a shelter. | User ID, shelter ID, representative information, authorization status. |
| Animal Listing | Information about an animal available for adoption. | ID, shelter ID, name, species, breed, age, sex, size, description, health information, status. |
| Animal Photograph | A photograph associated with an animal listing. | ID, listing ID, file reference, metadata. |
| Adoption Application | A request to adopt an animal. | ID, user ID, listing ID, submission date, status, relevant application data. |
| Volunteer Profile | Information about a volunteer. | User ID, location, help categories, availability, experience, verification status. |
| Assistance Request | A request for help sent to a shelter. | ID, requester ID, shelter ID, location, description, status, timestamps. |
| Volunteer Task | A defined activity requiring assistance. | ID, shelter ID, description, category, status, assigned volunteer, timestamps. |
| Fostering Request or Offer | A request or offer concerning temporary care. | ID, author, animal or shelter reference, description, status, timestamps. |
| Message | A message exchanged between authorized participants. | ID, conversation reference, sender, content, timestamp, read state. |
| Notification | An in-app or email notification event. | ID, recipient, type, content reference, timestamp, delivery state. |
| Administrative Record | A record of an administrative operation, where audit logging is implemented. | ID, actor, action, target, timestamp, result. |

## 7.2 Data Validation

- Required fields must be validated before the relevant record is saved.
- Email addresses must follow an accepted email format.
- Contact details must be validated according to their defined formats.
- Animal listing fields must distinguish required information from optional or unknown information.
- Uploaded photographs must be subject to file-type and size restrictions.
- Users must not be allowed to modify records outside their permissions.
- Status changes must follow the allowed transitions defined for each workflow.
- Location information must be validated according to the selected location-input method.

Exact field lengths, upload limits, formats, and status-transition rules remain to be defined.

## 7.3 Data Integrity

- Every animal listing must be associated with a shelter or another explicitly authorized owner.
- Adoption applications must reference the relevant user and animal listing.
- Volunteer tasks must reference the shelter or authorized creator responsible for them.
- Messages must be associated with a conversation and its authorized participants.
- Notifications must reference the intended recipient.
- Deletion and status changes must not leave invalid references in related records.

The final rules for cascading deletion, anonymization, and historical record retention must be defined before implementation.

## 7.4 Data Retention and Deletion

The platform will handle account information, animal listings, adoption applications, messages, and operational records.

The following decisions remain to be specified:

- Which records users can delete themselves.
- Whether account deletion results in physical deletion, anonymization, or retention of selected records.
- How messages and application histories are handled after account deletion.
- How long administrative records are retained.
- Whether expired or inactive listings are archived or deleted.
- Whether a specific announcement type must expire after a defined period.

Retention periods must be defined consistently with the applicable legal requirements and the platform's operational needs.

## 7.5 Personal Data and Privacy

The platform is expected to process personal data such as names, email addresses, telephone numbers, locations, and messages.

The implementation must define:

- Which data is required for each feature.
- Who can access each category of personal data.
- Which contact details are public and which are restricted.
- How user consent and applicable privacy requirements are handled.
- How account deletion requests are processed.
- How data is protected during transmission and storage.
- How access to administrative records is controlled.

Specific legal obligations and retention periods must be verified before the final SRS is approved.

---

# 8. External Interface Requirements

## 8.1 User Interface

The system shall provide a web interface suitable for public visitors, registered users, shelter representatives, volunteers, and administrators.

The interface shall provide:

- A public animal catalogue.
- Animal listing details and photographs.
- User registration and sign-in interfaces.
- User profile and application management interfaces.
- Shelter registration and listing management interfaces.
- Volunteer profile and task interfaces.
- Adoption application processing interfaces.
- Internal messaging interfaces.
- Temporary fostering interfaces.
- An administrative interface.
- A language selector supporting Estonian, Russian, and English.

The initial language shall be selected based on browser or device language settings where possible. Users shall be able to switch languages manually.

Detailed layouts, visual design, accessibility targets, and responsive breakpoints remain to be defined.

## 8.2 Software Interfaces and APIs

The final software interfaces and APIs have not yet been selected.

The implementation may require internal interfaces for:

- Account management.
- Shelter and animal listing management.
- Adoption applications.
- Volunteer tasks and fostering.
- Messaging.
- Notifications.
- Administrative functions.

Any API contracts, data formats, authentication mechanisms, and error-response formats shall be documented when the architecture is selected.

## 8.3 External Services

The following external integrations are expected to be considered:

| Service | Purpose | Status |
|---|---|---|
| Email delivery service | Send email notifications. | Required capability; provider not selected. |
| Geolocation | Obtain the user's location with permission. | Browser capability under consideration. |
| Mapping or geocoding service | Support location-based shelter suggestions. | Provider and integration method not selected. |
| External animal listing sources | Import animal listings. | Excluded from MVP. |
| AI service | Provide AI-powered animal matching. | Excluded from MVP. |

The use of Google services has been discussed, but the exact Google product, intended integration, costs, and privacy implications must be confirmed before the SRS can define a binding external-service requirement.

## 8.4 Communication Interfaces

- The system shall support communication between the web client and the application backend.
- Email shall be used for supported email notifications.
- Internal messaging shall be available to authorized participants.
- Location access shall require browser permission when browser geolocation is used.
- Communication protocols and transport-security requirements shall be specified during architecture design.

---

# 9. Non-Functional Requirements

The following requirements describe expected quality attributes. Quantitative targets must be established where they are currently unspecified.

## 9.1 Security

- The system shall enforce authentication for account-dependent features.
- The system shall enforce role-based authorization.
- The system shall prevent users from modifying records outside their permissions.
- The system shall protect private messages and personal information from unauthorized access.
- Administrative operations shall be restricted to authorized administrators.
- User input shall be validated on the server side where applicable.
- Passwords, if password-based authentication is selected, shall not be stored in plaintext.
- Sensitive data shall be transmitted securely in the deployed application.
- The system shall handle authentication and authorization failures without exposing sensitive internal information.

## 9.2 Performance

The system should provide responsive interaction for catalogue browsing, filtering, profile management, and routine form submissions.

Specific performance targets, including response times, expected concurrent users, and maximum data volumes, remain to be established.

## 9.3 Reliability and Availability

- The system should preserve data integrity during normal operation.
- Failed operations should provide understandable feedback.
- Notification delivery failures should not invalidate the underlying application or message record.
- Backup, recovery, availability, and downtime targets remain to be defined.

## 9.4 Usability and Accessibility

- The interface shall support Estonian, Russian, and English.
- Navigation and forms should be understandable to non-technical users.
- Validation errors should identify the affected input where possible.
- The interface should support common desktop and mobile browser usage.
- Accessibility standards and measurable conformance targets remain to be selected.

## 9.5 Compatibility

The system is intended to operate in modern web browsers.

The exact supported browsers, versions, and mobile-device requirements remain to be defined.

## 9.6 Maintainability and Testability

- Requirements shall be traceable to implemented functionality and acceptance criteria.
- The implementation should separate responsibilities sufficiently to support testing and maintenance.
- Core workflows shall be testable without relying exclusively on manual visual inspection.
- Business rules and status transitions should be implemented consistently.
- The project should maintain documentation for important architectural and integration decisions.

## 9.7 Scalability

The initial target region is Ida-Viru County.

The system should be designed so that future expansion to additional regions can be considered without requiring the entire application to be redesigned. Specific capacity targets and expansion requirements remain to be defined.

---

# 10. System States and Workflows

## 10.1 Animal Listing Workflow

The following is a preliminary workflow; the final set of statuses must be confirmed.

Potential states:

- Draft.
- Published / Available.
- Adoption in Progress.
- Adopted.
- Unpublished or Removed.

Important rule: an animal must not be marked as adopted solely because an adoption application has been approved. The shelter must confirm that the adoption has actually taken place.

The rules for withdrawing, archiving, deleting, or republishing a listing remain to be defined.

## 10.2 Shelter Registration Workflow

Expected workflow:

1. Registration submitted.
2. Pending review.
3. Additional information requested, if necessary.
4. Approved or rejected.
5. Resubmitted after correction, where applicable.

Only an approved shelter may manage animal listings.

## 10.3 Adoption Application Workflow

The system must support application submission, shelter review, communication with the applicant, status updates, and the final outcome.

The exact statuses and allowed transitions remain to be defined. Application approval and completed adoption must be represented as separate events.

## 10.4 Volunteer Verification Workflow

Expected workflow:

1. Volunteer profile submitted.
2. Verification pending.
3. Approved, rejected, or awaiting additional information.
4. Updated profile resubmitted, where applicable.

The system must enforce the permissions associated with the volunteer's verification status. The scope of shelter verification remains an open question.

## 10.5 Volunteer Task Workflow

The system must support task creation, volunteer responses, selection of an executor, progress tracking, and a recorded outcome.

Potential statuses include:

- Open.
- In Progress.
- Completed.
- Cancelled.

These statuses are preliminary and must be confirmed before implementation.

## 10.6 Temporary Fostering Workflow

The system must support shelter requests, volunteer offers, responses, communication, agreement on an arrangement, and a recorded outcome.

The exact states and the party authorized to confirm completion or cancellation remain to be defined.

## 10.7 Assistance Request Workflow

The system must support request submission, shelter selection, delivery to the selected shelter, and a shelter response.

The exact statuses, reassignment rules, and closure conditions remain to be defined.

---

# 11. Acceptance Criteria

## 11.1 Functional Acceptance Criteria

The MVP will be considered functionally acceptable when the following can be demonstrated:

- Guests can browse animal listings and apply supported search filters.
- Animal listings display their available descriptions and photographs.
- Ordinary users can register, sign in, and manage their profiles.
- Prospective shelters can submit registration requests.
- Administrators can review and approve or reject shelter registrations.
- Only approved shelters can manage their own animal listings.
- Administrators can manage listings across shelters.
- Registered users can submit adoption applications for multiple animals.
- Shelter representatives can review applications and communicate with applicants.
- Animal listings are marked as adopted only after shelter confirmation of the completed adoption.
- Users can create volunteer profiles and submit them for verification.
- Authorized reviewers can verify volunteers.
- Users and volunteers can submit assistance requests to selected shelters.
- The system can suggest a nearby shelter when sufficient location information is available.
- Shelters can create volunteer tasks, and eligible volunteers can respond.
- Shelters can publish temporary fostering requests, and volunteers can publish fostering offers.
- Authorized participants can communicate through the platform.
- The interface supports Estonian, Russian, and English.
- Supported events generate in-app notifications and email notification attempts.
- Administrators can manage accounts, shelters, volunteers, listings, and the specified basic statistics.
- Role-based permissions are enforced.

## 11.2 Non-Functional Acceptance Criteria

The following must be verified before final project acceptance:

- Unauthorized users cannot access protected functionality.
- Users cannot modify records outside their permissions.
- Private messages and personal information are restricted to authorized participants.
- Required data is validated.
- The interface can be used in the three supported languages.
- Core workflows behave consistently with the defined state transitions.
- The system handles routine validation and communication failures without corrupting data.
- Performance, browser compatibility, accessibility, and reliability meet the quantitative targets established before final acceptance.

## 11.3 Project Completion Criteria

The project can be considered complete when:

- All agreed MVP requirements have been implemented or formally marked as excluded.
- Functional requirements have corresponding tests or demonstrable acceptance checks.
- The main user workflows have been tested.
- Access control has been tested for each role.
- Known limitations and unresolved issues are documented.
- Required project documentation has been updated.
- The project supervisor's applicable delivery and evaluation requirements have been met.

---

# 12. Requirements Traceability

The following table provides preliminary traceability between major requirements, use cases, and acceptance criteria.

| Requirement ID | Requirement | Related Use Cases | Acceptance Reference |
|---|---|---|---|
| FR-001 | Browse and Search Animal Listings | UC-001 | 11.1 |
| FR-002 | Animal Listing Management | UC-001, UC-004 | 11.1 |
| FR-003 | Shelter Registration and Verification | UC-003 | 11.1 |
| FR-004 | User Registration and Account Management | UC-001, UC-002 | 11.1 |
| FR-005 | Adoption Application Management | UC-002 | 11.1 |
| FR-006 | User Profile and Application Overview | UC-002 | 11.1 |
| FR-007 | Volunteer Profile Management and Verification | UC-005 | 11.1 |
| FR-008 | Volunteer Assistance Requests | UC-006 | 11.1 |
| FR-009 | Volunteer Task Management | UC-007 | 11.1 |
| FR-010 | Temporary Animal Fostering | UC-008 | 11.1 |
| FR-011 | Internal Messaging and Contact Information | UC-002, UC-006, UC-007, UC-008 | 11.1 |
| FR-012 | Multilingual Interface | All applicable use cases | 11.1 |
| FR-013 | Notifications | UC-002, UC-003, UC-005, UC-006, UC-007, UC-008 | 11.1 |
| FR-014 | Platform Administration | UC-003, UC-005, UC-009 | 11.1 |
| FR-015 | Content and Account Moderation | UC-009 | 11.1 |
| FR-016 | Platform Statistics | UC-009 | 11.1 |

---

# 13. Open Questions

The following items require clarification before the SRS can be considered stable.

| ID | Question | Reason / Impact | Status |
|---|---|---|---|
| OQ-001 | What are the exact statuses and allowed transitions for adoption applications? | Required for consistent application processing. | Open |
| OQ-002 | What are the exact statuses and cancellation rules for volunteer tasks? | Required to implement task lifecycle and permissions. | Open |
| OQ-003 | Does shelter approval of a volunteer apply across the entire platform or only to that shelter? | Affects volunteer permissions and verification logic. | Open |
| OQ-004 | How are fostering requests and offers matched, approved, and closed? | Required for a complete fostering workflow. | Open |
| OQ-005 | How should volunteers coordinate searches for lost animals while public lost-and-found announcements are excluded from the MVP? | The current assistance categories and MVP scope need to be reconciled. | Open |
| OQ-006 | Will users be able to submit complaints, or is complaint functionality excluded? | The requirements discussion contains conflicting answers about complaints. | Open |
| OQ-007 | If complaints are supported, will they be reviewed manually, and what actions can administrators take? | Required to finalize moderation behavior. | Open |
| OQ-008 | Which Google service, if any, will be used for location, maps, geocoding, or email? | “Google” has been mentioned, but the intended product and integration are not yet precise. | Open |
| OQ-009 | Which fields are mandatory for an animal listing, and which may be unknown? | Required for validation rules and form design. | Open |
| OQ-010 | What are the exact retention and deletion rules for accounts, messages, applications, listings, and administrative records? | Required for data integrity, privacy, and lifecycle management. | Open |
| OQ-011 | Are any platform records subject to automatic expiration, and if so, which records and what expiration periods apply? | Expiration rules must be explicitly defined before they can be implemented consistently. | Open |
| OQ-012 | What is the exact process for account deletion, including the handling of related records? | Required to define the account lifecycle and data handling. | Open |
| OQ-013 | How should shelter eligibility be determined using email domains, and what happens when the domain is inconclusive? | Email-domain analysis alone may not reliably establish that an applicant represents a legitimate shelter. | Open |
| OQ-014 | What are the final authentication, account recovery, and session-management rules? | Required for implementation and security testing. | Open |
| OQ-015 | Which mapping or geocoding provider will be used, and what are its cost and usage limitations? | Required for reliable location-based shelter suggestions. | Open |
| OQ-016 | What are the target response times, expected concurrent users, backup requirements, and availability targets? | Required to make non-functional acceptance criteria measurable. | Open |
| OQ-017 | Which browsers and accessibility standards must be supported? | Required for compatibility and accessibility testing. | Open |
| OQ-018 | How will language preferences be stored, and what is the fallback language? | Required for consistent language selection across visits. | Open |
| OQ-019 | Which additional events should generate in-app and email notifications? | The currently confirmed events may not cover every workflow. | Open |
| OQ-020 | What are the final rules for message access, contact visibility, and administrative access to conversations? | Required to define privacy boundaries. | Open |
| OQ-021 | What are the exact statuses and closure rules for assistance requests? | Required for request tracking and reporting. | Open |
| OQ-022 | Which fields and supporting evidence are mandatory for shelter registration, and which verification rules apply? | Required for a consistent verification process. | Open |
| OQ-023 | What are the final measurable usability, performance, reliability, and scalability targets? | Required for objective acceptance testing. | Open |

---

# 14. Glossary

| Term | Definition |
|---|---|
| Adoption Application | A request submitted by a user to adopt an animal. |
| Adoption Completion | Confirmation by the shelter that an animal has actually been adopted. |
| Animal Listing | A record containing information about an animal available for adoption. |
| Approved Shelter | A shelter whose registration has been approved by an administrator. |
| Assistance Request | A request for help submitted to an animal shelter. |
| Guest | A visitor who is not authenticated. |
| Internal Messaging | A communication feature available to authorized platform participants. |
| MVP | The first version containing the agreed essential functionality. |
| Shelter Representative | A user authorized to act on behalf of an approved shelter. |
| Temporary Fostering | Temporary care of an animal before a longer-term arrangement is established. |
| Volunteer Task | An activity created to coordinate assistance from volunteers. |
| Volunteer Verification | The process of confirming that a volunteer is eligible for the relevant platform functionality. |

---

# 15. Change History

| Version | Date | Author | Description |
|---|---|---|---|
| 0.1 | 2026-10-19 | Ivan Petrov, Maksim Koroljov | Initial preliminary SRS based on the requirements elicitation. Unresolved decisions are recorded in Section 13. |
| 0.2 | 2026-10-20 | Ivan Petrov, Maksim Koroljov | Removed an unrelated ANPR glossary entry and rewrote OQ-011 to avoid treating an unconfirmed 30-day expiration period as an established requirement. |
