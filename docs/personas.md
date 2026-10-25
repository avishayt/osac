# OSAC Personas

These are the essential personas that OSAC must target for an MVP. Many
additional personas can be identified within the solution space, some of which
will be added to this document over time as the project is ready to address
their unique use cases.

Personas describe users' goals and responsibilities. Authorization is defined
separately through roles, capabilities, and scope. A person performing some
responsibilities associated with a persona does not necessarily receive all
permissions associated with it. The responsibilities below are subject to the
user's assigned permissions and scope; a persona name alone grants no access.

Feature requirements should specify the capabilities and scope needed by each
affected permission variant. For example, an audit reader may need access to
evidence within one tenant or an explicitly authorized provider scope, without
permission to manage resources, users, or audit configuration. Tenant-scoped
roles must preserve tenant isolation. Each feature PRD defines which access
requirements its release supports.

An Auditor or read-only role does not by itself require another canonical
persona. Add a persona when OSAC needs to address distinct goals or workflows.

## Cloud Provider Admin

* works for the Cloud Provider
* handles or facilitates tenant onboarding
* sets quotas for tenant organizations
* uses the OSAC interfaces to manage tenant organizations
* uses the OSAC interfaces to manage resource allocation
* can access tenant organizations within an explicitly authorized provider scope
* manages any global catalogs of templates (VM templates, cluster templates, etc)
* ensures that all global templates work with the local infrastructure
* works with internal infrastructure owners (Cloud Infrastructure Admins) as necessary

## Cloud Infrastructure Admin

* works for the Cloud Provider
* manages a part of core infrastructure, possibly including network, firewall, compute resources, storage, etc.
* ensures that cloud services are running, including the cloud control plane
* integrates the cloud control plane with local infrastructure including specific compute hardware, DNS systems, storage solutions, etc.

## Tenant Admin

* works for the Tenant Organization
* typically does not have any relationship to other tenants of the cloud provider
* manages their organization's configuration in OSAC, including IDP
* manages users within their organization
* manages quotas within their organization
* can only see users and resources associated with their own organization
* manages organization-specific catalogs of templates
* controls which global templates are visible to tenant users

## Tenant User

* works for the Tenant Organization
* can utilize templates from global and organization-specific catalogs
* self-service provisions cloud resources for use by themself or their team
* manages the full lifecycle of cloud resourses
* can see quota utilization that would apply to them
* may prefer click-ops, but wants an API and CLI for optional automation
