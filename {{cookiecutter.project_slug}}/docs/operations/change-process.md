# Change Management Process for {{cookiecutter.project_name}}

Change Management in {{cookiecutter.project_name}} follows organizational IT management processes and change control procedures.

- We follow the organizational operating model for GD&AI IT Solutions
- If changes alter or can alter GxP data, the change will be duly authorized by {{cookiecutter.system_owner_name}} or delegate
- For practical details on how we run the development process please refer to the {{cookiecutter.project_name}} developer handbook.

## Use of {{cookiecutter.development_platform}}

{{cookiecutter.development_platform}} is used as the development platform for storing, tracking, and collaborating on software projects. As a central component, it provides a Git repository for storing files (e.g. code and documentation). Git is used by millions of users around the world as the industry standard for repositories and is considered best IT practice.

{{cookiecutter.project_name}} uses {{cookiecutter.development_platform}} as the ticketing system to anchor IT changes as well as for handling approvals, even though {{cookiecutter.development_platform}} is currently only verified for non-GxP activities. This section provides the rationale for {{cookiecutter.project_name}}’s use of {{cookiecutter.development_platform}} despite {{cookiecutter.project_name}} being classified as GxP infrastructure. We have selected to utilize {{cookiecutter.development_platform}} as a documentation tool for the {{cookiecutter.project_name}} project due to its status as the leading, most mature and established tool for supporting software development.

### GAMP5 Classification of {{cookiecutter.development_platform}}

{{cookiecutter.development_platform}} is considered a ”Tool” in GAMP5 terminology:

_”Tools and systems supporting life cycles, IT processes, and infrastructure (rather than directly supporting product life cycle processes) are not themselves GxP regulated systems and should not be subject to specific validation but managed by routine company assessment and assurance practices and good IT practices”_

Hence, we do not need to qualify {{cookiecutter.development_platform}} itself. Instead, we will consider if we should implement controls to mitigate that {{cookiecutter.development_platform}} is not verified for GxP activities.

### {{cookiecutter.project_name}} activities and rationale

The following table describes the {{cookiecutter.project_name}} activities that are relevant for establishing and maintaining the qualified state of {{cookiecutter.project_name}}, as well as the supporting artefacts used in {{cookiecutter.development_platform}}:

| **Project activity**                                                                                                                                                                                                                             | **Supporting artefact in {{cookiecutter.development_platform}}** |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------- |
| Documentation of intended use description, requirements, design specifications, configuration specifications, verification test cases, installation guides, configuration guides, O&M description, IT recovery plan, and IT recovery test report | Files in Git                      |
| Documentation of IT change                                                                                                                                                                                                                       | Issue in {{cookiecutter.development_platform}}                   |
| Reporting of manual test cases                                                                                                                                                                                                                   | Comment on {{cookiecutter.development_platform}} Issue           |
| Solution Owner/delegate approval of IT change                                                                                                                                                                                                    | Status of {{cookiecutter.development_platform}} Issue            |
| IT QA approval of IT change, if relevant                                                                                                                                                                                                         | Comment on {{cookiecutter.development_platform}} Issue           |
| Solution Owner/delegate approval of requirements                                                                                                                                                                                                 | Approval of pull request          |
| Solution Owner/delegate approval of verification reports                                                                                                                                                                                         | Pipeline run of {{cookiecutter.development_platform}} actions    |
| IT QA approval of O&M description                                                                                                                                                                                                                | Pipeline run of {{cookiecutter.development_platform}} actions    |

The {{cookiecutter.development_platform}} artefacts mentioned in the table above are currently only verified for use in non-GxP activities. The following provides the rationale for why {{cookiecutter.project_name}} uses them for GxP activities:

**Files in Git**

Git is the de facto standard version control system in the world. It is the most widely used source-code management tool among professional developers. The likelihood of documents in Git being lost is extremely low. In addition, it is in the nature of Git, that repositories are cloned among the developers involved, meaning that even in the rare case that files should be lost from Git, it will be easily recoverable from one of the other clones.

**Issues in {{cookiecutter.development_platform}}**

We anchor our IT changes as {{cookiecutter.development_platform}} Issues, and use the comment section and status field to document our verification report for manual test cases and various approvals. Hence, {{cookiecutter.development_platform}} Issues are critical to document the qualified state of {{cookiecutter.project_name}}. We see three risks to our use of {{cookiecutter.development_platform}} Issues:

1.  Issues in {{cookiecutter.development_platform}} can be permanently deleted by {{cookiecutter.development_platform}} admins.
2.  Comments on {{cookiecutter.development_platform}} Issues can be permanently deleted by {{cookiecutter.development_platform}} admins. Note that any other change to comments is always traceable through the comment’s history.
3.  An Issue may be lost through a disaster event in {{cookiecutter.development_platform}}, which could potentially not be fully recoverable by {{cookiecutter.development_platform}}.

To mitigate the above, we have considered making an export of IT changes to PDF and store the export in Git (or a similar safe storage location) after the IT change has been released and closed. The export would include descriptions, status changes, and comments and would thus capture all information of the IT change. From a risk-based approach we have decided _not_ to implement this mitigation for the following reasons:

- We will instead mitigate bullets 1 and 2 above by restricting the {{cookiecutter.development_platform}} admin roles to only core members of the project team. This will ensure that the risk of accidental or deliberate deletion of Issues or Issue comments is sufficiently mitigated.
- The risk of bullet 3 occurring is extremely low, as {{cookiecutter.development_platform}} is relied upon by millions of professional developers around the world, and no such incidents have been widely reported by the community.

The residual risk we accept by this is limited in time, as the {{cookiecutter.development_platform}} project in Novo Nordisk plans to verify {{cookiecutter.development_platform}} for GxP activities by end of 2024.

**Pull requests in {{cookiecutter.development_platform}}**

We use pull requests to document approval of documentation including requirements by Solution Owner/delegate. Pull requests are always kept by {{cookiecutter.development_platform}} for as long as the project exists. The _likelihood_ of a pull request being lost is very low. Even if a pull request should get lost, we know from the use of the QMS Pipeline, that the pull request for a release must have been created and approved due to the existence of the release in production (by nature of the QMS Pipeline). We also know that the QMS Pipeline will include solution owner/delegate as approver in case there are changes to requirements. Hence, from a risk-based approach the _impact_ of losing a pull request is also very low. In conclusion we accept the residual risk of losing a pull request.

**Pipeline runs in {{cookiecutter.development_platform}}**

We use pipeline runs to document certain approvals, including verification reporting of automated test cases. Pipeline runs are always kept in {{cookiecutter.development_platform}} for as long as the project exists. The risk of a pipeline run being lost is very low. If a pipeline run is lost, we would not be able to document when and by whom verification report and O&M description was approved. We would, however, still be able to prove that the two artefacts were in fact approved, as this would be a prerequisite for approval of the release and close of the IT change.

### Conclusion

From a risk-based approach we accept to use {{cookiecutter.development_platform}} to support the qualification of {{cookiecutter.project_name}}, even though {{cookiecutter.development_platform}} is currently only verified for non-GxP activities.

We will revisit this assessment once {{cookiecutter.development_platform}} is verified for GxP activities by the {{cookiecutter.development_platform}} project in Novo Nordisk.
