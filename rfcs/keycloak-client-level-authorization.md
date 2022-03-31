# Keycloak client level authorization

| Status        | (Proposed / Accepted / Implemented / Obsolete)       |
:-------------- |:---------------------------------------------------- |
| **RFC PR #**     | [NNN](https://github.com/AOT-Technologies/forms-flow-ai/pull/NNN) (update when you have PR #)|
| **Author(s)** | Sumesh Kariyil (sumesh.pk@aot-technologies.com) |


## Objective

Formsflow.ai currently works based on keycloak group authorization. This as a Request For Comments on changing the approach to client based authorization.

## Motivation

There are organizations who would want to use same keycloak realm (shared realm) for multiple installations of formsflow, with authorization specific to each installation.

## Design Proposal

Formsflow would continue supporting keycloak groups from a backward compatibiltiy point of view, but will support client level authorization by changing the authorization to keycloak client. Each installation would get it's own set of keycloak clients and user roles are managed under keycloak client.

### Code Changes:
- Change camunda code to work with client level roles
- Change analytics authorization mapping to keycloak clients
- Use roles instead of groups in any place which uses groups now

### Keycloak changes
- Need an empty camunda-admin group, no one needs to be assigned : To avoid this, need to make lot of changes on camunda plugins which may cause issue with version upgrades later.
- 3 clients needs to be created per project. 
	- <project-identifier>-forms-flow-web with audience mapper of same name
	- <project-identifier>-forms-flow-bpm (Service account) with audience mapper of <project-identifier>-forms-flow-web and <project-identifier>-forms-flow-bpm 
	- <project-identifier>-forms-flow-analytics with audience mapper of same name
- Default 4 roles under <project-identifier>-forms-flow-web
	- forms-flow-designer
	- forms-flow-client
	- forms-flow-reviewer
	- camunda-admin
- Any additional client roles can come under web or <project-identifier>-forms-flow-analytics client as per project requirement.
- <project-identifier>-forms-flow-bpm needs service account access with roles:
	- manage-clients
	- manage-users
	- query-clients
	- query-users
	- view-users


### Alternatives Considered

### Performance Implications
None at this moment.

### Dependencies




### Compatibility (Existing implementation Impact)

## Detailed Design

TBD

## Thanks

Thanks to tensforflow, react RFC templates.