# IT Incidents and IT Problems for {{cookiecutter.project_name}}

IT incidents are handled in alignment with organizational guidelines for managing IT incidents. IT incidents are assessed by {{cookiecutter.system_owner_name}} or delegate. When an IT incident is suspected to be a security incident, it is escalated to the appropriate security team.

Problem management i.e., root cause analysis is conducted in post mortems (see [post mortem ADR](https://foundation.data.novonordisk.cloud/ADRs/accepted/0012-post-mortems/#status)) and published on

```yaml
[Product Website](URL to post-mortems).
```

Users communicate their challenges (not defined as incidents yet) through heterogeneous communication channels (monitoring, email, teams, in person). If the {{cookiecutter.project_slug}} team define a user challenge as an incident, this is in turn registered in ServiceNow and assigned with the below properties:

```yaml
- Business Application ID: [Business Application ID (Friendly Product Name)]
- Service Offering: [Service Now Service Offering]
- Assignment group: [Service Now Assignment Group]
```

Incidents are communicated to stakeholders according to our

```yaml
example: [user communication process](./user-management/user-communication.md)

[user communication process](URL to user communication process).

```

as well as the default notification via ServiceNow.

Incidents might also be [communicated by our IT vendor](./vendor-management.md). For vendor communication received by email that impacts the service performance, compliance or the IT Risks, an incident must be created in SNOW.

## Vendor Support

```yaml
example:
Incidents that are believed to be caused by the {{cookiecutter.project_name}} SaaS platform should be raised as tickets on the [{{cookiecutter.project_name}} Support site](https://support.{{cookiecutter.project_slug}}.com/support/s/login/).

It is a pre-requisite that user has been registered on the support platform which is done by writing to our {{cookiecutter.project_name}} account manager.

Novo Nordisk has purchased the **Enterprise Support** package and the response times and support level is defined in [{{cookiecutter.project_name}} Support Policy](https://www.{{cookiecutter.project_slug}}.com/wp-content/uploads/2022/07/{{cookiecutter.project_name}}-Support-Policy-SLA-March-2022.pdf).
```

## Data breach

The Solution owner (or delegated) is accountable for ensuring that data breach is handled according to Novo Nordisk guidelines.

In case a data breach is discovered we use the following steps [PD.1.15]:

1.  Notify Team, Product Owner, Solution Owner.
2.  Any data breaches must be reported immediately to the [compliance hotline](https://novonordisk.sharepoint.com/sites/BusinessAssuranceV0012/SitePages/Data-Breach-Response-.aspx).
3.  assess to the best of our ability the extent of the breach, including what data has been compromised.
4.  Take steps to contain the breach to prevent further unauthorized access or data loss. This may involve isolating affected systems or networks.

It is recommended to conduct a [post mortem](../post-mortem/post-mortems/post-mortem-template.md) to identify cause of breach and how to prevent it in the future.

Data breached might also be [communicated by our IT vendor](./vendor-management.md).
