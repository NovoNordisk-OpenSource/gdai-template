# Implementation Plan {{cookiecutter.project_name}}

<!---
This "Markdown" file has the source text for the implementation plan pdf that is uploaded to and in QualityDocs.

The implementation plan must be approved in QualityDocs because Novo Nordisk's IT Process currently requires an S-signature for the implementation plan,
and this type of signature cannot be performed with approvals in Azure DevOps (e.g., pull requests and manual approvals in a pipeline execution cannot count as S-signatures).

The team makes revisions to the implementation plan in this file first, and when the team are satisfied with the revision,
they convert the Markdown file to pdf.

In other words, this file is equivalent to a docx file that the team collaborate in before they export to pdf and sign in QualityDocs.

Note these differences between the Markdown file and the QualityDocs pdf:
1. this introductory comment does not appear in the converted PDF file
2. the table of contents does not appear explicitly in this pdf, but is generated for the pdf.
-->

**This document is signed electronically using QualityDocs.**

**Signatures appear on a separate signature page.**

| Table of Signatures              |                          |                             |
| -------------------------------- | ------------------------ | --------------------------- |
| **Prepared by:**                 |                          |                             |
| Author                           | {{cookiecutter.author_name}}      | {{cookiecutter.author_initials}}     |
| **Approved by:**                 |                          |                             |
| IT System Owner <br> or delegate | {{cookiecutter.system_owner_name}}  | {{cookiecutter.system_owner_initials}} |
| QA                               | {{cookiecutter.qa_name}} | {{cookiecutter.qa_initials}}    |

## Definitions

| **Term** | **Definition**                                                                                                                                                                                                                                     |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Artefact | Any document, diagram, file, or other piece of information that is produced, modified, or used during the software development process. This includes items such as requirements documents, design specifications, and test plans.                 |
| CI       | Continuous Integration is a development practice where developers regularly merge their code changes into a central repository. This process is followed by automated builds and tests.                                                            |
| CD       | Continuous Delivery is the practice of ensuring that the system is always in a deployable state, and that every change could potentially be released to production at any time. Continuous Delivery automates and streamlines the release process. |
| Tool     | Software used to support development, operation or maintenance of the software product. Tools are not part of the finished software product.                                                                                                       |

For general abbreviations, refer to _IT definitions and abbreviations [[Q0871716](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/2398949)]._

## Scope

This document is an implementation plan that describes the activities to ensure {{cookiecutter.project_name}} is fit for the intended use,
as required by _Manage IT Systems including digital solutions [[Q187219](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/167978)]_.

The plan describes a way of working and covers multiple releases that are delivered on a continuous basis.

All releases are assessed to determine if a GxP merge request is required according to _Change Control [[Q220205](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/163531)]_.

Implementation reports will be written for each release, and reporting is always done against the most current version of this implementation plan.

Each implementation report will reference the related CR case(s) when required by _Change Control [[Q220205](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/163531)]_.

The plan is continuously evaluated to always reflect how the team is working. Changes to the original project scope will be evaluated for impact on the planning established in this document.

## Roles and responsibilities

The generic responsibilities in _Manage IT Systems including digital solutions [[Q187219](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/167978)]_,
_Ownership of IT systems and IT infrastructure [[Q187218](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/167977)]_ and
_protecting and handling information [[Q190751](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/168341)]_ are used, unless otherwise specified.

| Organization | Role                   | Initials                      | Comments |
| ------------ | ---------------------- | ----------------------------- | -------- |
| NN LoB       | System Owner           | {{cookiecutter.system_owner_initials}}   |          |
| NN LoB       | Data Owner             | {{cookiecutter.system_owner_initials}}   |          |
| NN           | Project/System Manager | {{cookiecutter.project_manager_initials}} |          |
| NN           | Peer                   | {{cookiecutter.peer_reviewer_initials}}    |          |
| NN           | QA                     | {{cookiecutter.qa_initials}}      |          |

> **Table 1:** Roles and responsibilities.

## Supported Business Process

> [!TIP]
> The "Supported Business Process" section should provide a comprehensive overview of the processes that are supported by the system or project.
> This includes detailing which steps are supported by business process.
> For instance, this section could describes how environmental monitoring is conducted through regular sampling of air, surfaces, and personnel.
> It could also reference relevant documentation and System Description in ServiceNow.

## System Overview

> [!TIP]
> This section should provide a high level overview to illustrate the scope and boundary of the system covered by the plan.
> It should also include any interfaces to other systems.

## Initial Risk Assessment

> [!TIP] > {{cookiecutter.project_name}} is supporting a GxP regulated process. Add a high level statement on software category.

Generic IT risks related to data integrity, security, privacy are covered in the IT Risk Assessment Tool (ITRA) and Privacy management tool (PMT) for {{cookiecutter.project_name}}.

## Development and Implementation Strategy

## Delivery Workflow

Software will be developed, deployed and maintained with a 12-stage workflow, that is based on the principles of continuous integration and continuous delivery.

At each stage in the workflow, more extensive and higher-level tests are performed, providing increased confidence in the committed changes as the software progresses through the workflow.

| **#**  | **Stage Name**        | **Description**                                                                                                                                                                                                                                                                                                                                                                                                             | **Primary** **Roles**         |
| ------ | --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| **1**  | Authoring Change      | A member of the development team initiates changes within a local development environment. Code and configuration are updated in parallel with requirements, test cases, risk assessments, and other documentation. The intent is to keep the system in a continuously compliant state, by integrating quality and risk management activities for each small change. The changes should be no larger than two days of work. | Team member                   |
| **2**  | Pre-Commit            | A fully automated stage, where the changes made by the author are subjected to automated unit tests and other static testing. This includes running an automated tool that verifies that the changed code adheres to project standards and best practices (see [Code Review](#code-review)).                                                                                                                                | Automated                     |
| **3**  | Merge Request         | The proposed changes are reviewed and approved by a peer in the development team. For changes that affect user requirements, System Owner (or Delegate) and QA also approves. For other changes, any member of the development team can act as approver.                                                                                                                                                                    | Team member                   |
| **4**  | Commit                | A fully automated stage with no manual activities. It serves as an automated gate that gives fast feedback on the viability of the changes, not to execute complete test portfolios. An automated build process generates immutable artifacts, such as PDF documentation and software. This step is time-boxed (few minutes) and executes as many unit and integration tests as possible within the time-box.               | Automated                     |
| **5**  | Acceptance            | Execution of automated tests that cover unit and integration tests that were not able to be completed within time-limits of previous step. Acceptance also includes system level end-to-end testing, and is performed in a production-like test-environment.                                                                                                                                                                | Automated                     |
| **6**  | Extended Testing      | N/A, not used in the current project. Used when there is a need for horizontal system level testing.                                                                                                                                                                                                                                                                                                                        | Automated                     |
| **7**  | Exploration           | Ongoing exploratory testing of the current release candidate, in a demonstration environment.                                                                                                                                                                                                                                                                                                                               | Can vary                      |
| **8**  | Start Release         | A separate branch is created with a locked feature set for the next deployment to production.                                                                                                                                                                                                                                                                                                                               | Team member                   |
| **9**  | Release Approval      | The Release Branch is approved for **Deployment** and **Release** by QA and System Owner (or delegate). A set of reports are generated to inform the decision to release (see [Release Approval](#release-approval)). All releases will go through the **Release Approval** step, where a complete set of updated documentation will be generated and approved.                                                             | QA System Owner (or delegate) |
| **10** | Production Deployment | Manually initiated automated deployment to the production environment.                                                                                                                                                                                                                                                                                                                                                      | Team member                   |
| **11** | Live                  | Continuous monitoring of the software for optimal performance and reliability.                                                                                                                                                                                                                                                                                                                                              | Team member                   |
| **12** | Release Toggling      | The team can decide for every piece of functionality to separate deployment and release with feature flags. With feature flags changes can be activated in the live production system after release, without changing the system code. The timing can be decided by the system owner (or delegate), since authorization to release is formally given by approval of the release report in **Release Approval**.             | System owner (or delegate)    |

Throughout the workflow, close cooperation between all stakeholders is expected.

## Approval Gates

Three stages of the workflow (**Merge Request**, **Release Approval**, **Release Toggling**) are manually controlled gates that are used for the approvals required by the quality system.

- **Pull request review** ensures that every change to the IT solution and the related documentation is traceable to an author and approved by a Peer.
  When the changes are related to User Requirements, the pull request must be approved by QA and System Owner (or delegate).
- The Final Design Review, Performance verification, Implementation Report and authorization to release is approved by QA and System Owner (or delegate) in the **Release Approval.**
- The timing of the **Release** is decided by the System Owner.

## Configuration management

A version control functionality hosted in {{cookiecutter.development_platform}}, called Git, will be used to manage application code, infrastructure (as code), specifications, documentation, and other configuration items.

Git is the underlying technology used in {{cookiecutter.development_platform}} [^1]

[^1]: Azure DevOps ServiceNow ID: 10658 / GitHub ServiceNow ID: 12138.

Every change made in a Git repository must have an associated description of the change.

This provides the ability to track what changes were made, by who, and why they were made.

Git keeps a history of all revisions of the software and makes it possible to recreate the state of the system as it was at any point in time, whenever needed.

Sensitive configurations, such as passwords are confidential and must not be stored unencrypted in the Git repository.

Instead, they are kept in secret managers {{cookiecutter.secrets_store}} which are accessible only to authorized personnel.

The Quality System requires that the below artifacts are controlled in specific IT systems.

A list of all documentation stored in external systems must be maintained and made available as part of _Release Approval_.

This includes at least:

| **Artifact**                                                                                        | **Mandatory Location**        |
| --------------------------------------------------------------------------------------------------- | ----------------------------- |
| IT System Registration, System Description, IT Risk Assessment, IT Incidents                        | ServiceNow                    |
| Implementation Plan, Implementation Report, Operation and Maintenance SOP, Audit trail/traceability | Veeva Vault                   |
| Privacy mapping of business process                                                                 | Privacy Management Tool (PMT) |
| Merge Request (for changes with GxP impact)                                                         | NovoGLOW                      |

## Environments

| **Environment name**                    | **Activities**                                                                                                                                                                                                                                                                                                                                        |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Development                             | Local Development Environment. This is where developers initiate changes, write code, and perform pre-integration testing. Used in: Step 1 (Authoring Change) and Step 2 (Pull request).                                                                                                                                                              |
| Production-Like-Test-Environment (PLTE) | Production-like Test Environment (PLTE). This environment mimics the production setup as closely as possible. It's used for more comprehensive automated testing on the system level. If some production data sources or dependencies are not available, suitable mockups should be employed. Used in: Step 5 (Acceptance) and Step 6 (Extended test) |
| Demonstration Environment               | Demonstration Environment. This environment also mimics the production setup as closely as possible but is used for ongoing manual exploration of the software. Used in: Step 7 (Exploration)                                                                                                                                                         |
| Production Environment                  | Purpose: This is the live environment where the software runs and serves end users. Used in: Step 10 (Deployment), Step 11 (Live), and Step 12 (Release)                                                                                                                                                                                              |

Apart from production and demonstration, the environments are created and removed on-demand, as part of the delivery workflow.

An assessment of the differences between Production and the Production-like test environments (PLTE) is part of the verification reports, that is generated as part of **Release Approval**.

## Code Review

To ensure the software code is of high quality and meets predefined standards, the project will use a combination of automated tools and a traditional code review performed by a Peer.

A static code analysis tool will analyze the source code to identify potential errors, bugs, stylistic errors, and other issues.

The code analysis tool is used to enforce coding standards and best practices, making the code more readable, maintainable, and less prone to errors.

The code analysis tool is automatically activated during **Pull request**.

The tools configuration and the result of the analysis will be retained and summarized in a development report (see [Release Approval](#release-approval)).

In addition to the code analysis tool, a Peer will perform a code review as part of the pull request approval to ensure that code meets the specified requirements,
design constraints and correctly implements the intended functionality.

Approval of the pull request constitutes the documentation for the code review.

## Specifications

The project will use feature files to systematically collect and organize requirements, acceptance criteria, specifications, test instructions, and risks assessment related to a specific feature.

The feature files should be created in a close collaboration between QA, LoB SME, team members and System Owner (or delegate).

This ensures that all relevant aspects, such as technical, compliance and business concerns are considered.

Feature files use specific keywords such as Feature, Scenario, Given, When, Then, And, and But to structure the descriptions.

<pre>
Feature: [Brief feature description]
Scenario: [URS-01 Scenario description] @GXP @CriticalAspect
Given [Initial context]
When [Event occurs]
Then [Ensure some outcomes]
And [Additional steps]
</pre>

The scenarios represent the user requirements, and when necessary, additional scenarios can be added to also cover functional specifications (FS) and design specifications (DS).
The given/when/then format ensures that requirements are testable.

User Requirements are at the uppermost level and must reflect the intended use (problem to be solved) for the complete software product.
Each requirement must be tagged, when the source is GxP or Critical Aspect (for GMP).

Feature files are plain text files, that are stored in the same repository as the system code.

## Functional Risk Assessment (ITRRA)

A functional risk assessment is mandatory, when any of the requirements in a feature file is tagged with "GxP".
In this situation, a risk assessment is added to the feature file.

This risk assessment includes

- What could go wrong with the feature
- Cause(s) and likelihood: Unlikely (<30%), Possible (30-70%), Likely (>70%)
- Impact on the supported process: Insignificant, Moderate, or Critical impact on Product, Patient, Data Integrity
- Risk controls
- The net/gross risks are classified as @High, @Medium or @Low.

<pre>
Risk: unapproved samples
There is a risk that [some samples results are not displayed]
Because [the results are not approved in the lab yet] @Likely
Which could result [in misinterpretation of the results] @Moderate
Gross Risk: @High
Controls: Include a status message in the UI to alert users
Net Risk: @Low
</pre>

The risk controls may take various forms, for example, additional (new) requirements, additional test scenarios, end user training or even generic risk controls from the ITRA.

For all requirements tagged as "GxP" there must be test scenarios for negative testing and/or challenge tests or a justification for why only positive test is performed.

## Verification

The delivery workflow (see [Development and Implementation Strategy](#development-and-implementation-strategy)) relies on test automation to provide developers with rapid feedback on their code changes.

The scenarios in the feature files are translated into automated test cases, using the same given/when/then format.

The scenarios that reflect user requirements are approved by the Quality Unit and the System Owner (or delegate) in the stage **pull request review**.

Additional, lower-level test cases, such as unit tests, are created and maintained by the team without involvement of QA or System Owner (or delegate).

The delivery workflow enforces that the software is built only once (during **Commit**), and then progressively tested more extensively at each stage.

This means that the software being tested during development activities is identical to the software subsequently deployed to production, except for environment-specific configurations.

The high degree of control over the software development allows test activities from the software development process to be re-used as the verification tests (IV/OV/PV),
this is required by _Manage IT Systems including digital solutions [[Q187219](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/167978)]_.

The evidence for the successful deployment to the production-like test environments and production environment will be retained as evidence of installation verification (IV). [^2]

[^2]: Concretely, we can output, e.g., "deployment was successful" after deploying, because being able to successfully deploy implicitly counts as Installation Verification.

## Defects

If the test fails during any of the test stages, this will prevent the change from proceeding to the next stage, and thereby automatically prevent it from being released.

Any failure prompts an investigation to find and resolve the defect, for example updating a test case. Since all specifications and tests are controlled in the repository,
the defect investigation and resolution are documented in the step **Authoring Change.**

When an author submits a fix for a defect to the controlled repository (trunk) the change description must at least include the following information

- The word "defect" must be part of the title (to allow searching later)
- describe what happened
- investigate and describe the cause
- describe the actions taken

If a test of a requirement marked as Critical Aspect fails after **Branch to release**,
it must be managed as a validation deviation according to _Manage IT Systems including digital solutions [[Q187219](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/167978)]_.

## Release Approval

At the release approval, a set of information must be available in a format that enables outsiders to understand the history of the development process, e.g., a non-technical, human-readable PDF.

- Requirements Specification (URS)
- Design Specifications (FS, DS, CS)
- Architecture drawing
- Functional Risk Assessment (ITRRA)
- Feature Files (URS, FS, DS, CS, ITRRA - one document for each feature)
- Final Design review
- Development tests summary (code review, static code analysis, and unit tests)
- Traceability from feature file to related test(s)
- Verification (IV/OV/PV) reports including an assessment of differences between production-like test environment and production environment
- List of tools used during the development and assessment of their adequacy.
- List of external suppliers, and internal service providers, including supplier assessments, agreements, and how the services are monitored
- Implementation report, including:
  - Release notes, with a description of changes since the last deployment.
  - Decision on overall change type (normal, standard or emergency)
  - Impact on the supported business process
  - Reference to CR(s) in novoGLOW (if needed).
  - conclusion on the planned activities and any major changes to the planning
  - List of artifacts in external systems (e.g., O&M SOP, ITRA), and evaluation of their continued validity.
  - any outstanding activities
  - conclusion on fitness for intended use.
  - Description of process for deployment to production environment (pIV)
  - authorization to deploy and release

The IT Solution will be **released for deployment and use**, when release approval is approved by QA and System Owner (or delegate).

At the release approval all deliverables and documentation can be inspected as needed.

The release report and all other deliverables defined in this section must be uploaded and signed in VaultQuality not later than one week after **Release Approval**.

Approval of the implementation report in VaultQuality does not block release,
since intermediate approval is provided by QA and System Owner (delegate) as part of **Release Approval** (see _intermediate approval_ in _Manage IT Systems including digital Solutions [[Q187219](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/167978)]_).

## Roll back plan

If issues are detected after deployment, the rollback process can be initiated. The decision to initiate a rollback must be taken by the System Owner (or Delegate).

QA must be informed as soon as possible, although documentation for the information is not required since QA approves the release (of the roll back).

- Identify the last stable version (typically last release) in the repository.
- The code is built and tested to ensure it is still valid.
- If all tests pass, the previous version is deployed to the production environment.

After rollback, the system must be closely monitored to ensure the previous version is functioning correctly.

## IT Infrastructure

The software product may rely on IT Infrastructure components that are not considered as part of the software product itself and managed by another NN business unit or a supplier.

Such services are out of the scope of this plan and are qualified separately as defined in _Manage IT Infrastructure [[Q216301]](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/150851)_.

All infrastructure that is part of the software product is managed according to _Manage IT Systems including Digital Solutions [[Q187219](https://novonordisk-qualitydocs.veevavault.com/ui/#doc_info/167978)]._

## External Suppliers and Internal Service Providers

When internal or external suppliers are used, a specification of the services provided must be available.

This can take the form of a service description or a formal agreement, depending on the risk and complexity of the service provided.

The services provided must be monitored in the production environment (automatic or manual).

A list of internal/external suppliers, agreements, and how the services are monitored will be maintained and made available as part of **Release Approval.**
