# Open Source Policy Template

## Objectives

PUBLIC_ADMINISTRATION's goals in releasing this policy are:

* Comply with regulations

* Collaborate between national and international public administrations

* Engage with existing communities

* Foster economic growth

The objective of this policy is to allow PUBLIC_ADMINISTRATION to embrace open source software development without compromising its core interests and information security, following the communities’ best practices and in the respect of all stakeholders.

Globally this policy proposes to:

1. Allow civil servants and subcontractors to contribute and release open-source projects 

2. Share best practices to collaborate and engage with communities

3. Provide support and assistance

## Scope and applicability

This policy should be applied by all civil servants of PUBLIC_ADMINISTRATION and related contractors and subcontractors.

Entities belonging to ENTITY_NAME may instantiate an inherited version of this policy.

Open-sourcing existing code is another process and requires additional steps that are out of the scope of this policy. Please refer to the ENTITY_SUPPORT_EMAIL for more information.

Note that FOSS projects may include technical and functional documentation, user, administrator and/or programmer manuals, examples, translations, sample data, artwork, and/or configuration files. 

## Definitions

"FOSS" refers to “Free/Open Source Software” and is used generally to refer to software that either under a license that has been approved by the Free Software Foundation, Open Source Initiative, or a license which grants the four rights: to use the software for any purpose, to study the source code, to share it with others, and improve the software. In places “open source” is also substituted for readability. Free Software and Open Source Software are used as synonyms throughout the document.

"Civil servant": person employed by a public administration, either officially sworn in or on an employment contractual basis.

"OSI approved license:" [https://opensource.org/licenses](https://opensource.org/licenses)

"Free Software Foundation approved license": [https://www.gnu.org/licenses/licenses.en.](https://www.gnu.org/licenses/licenses.en.html)[html](https://www.gnu.org/licenses/licenses.en.html)

"Version control system": software product or service designed to store and retrieve several versions of source code and related assets in a consistent way, can be centralised,  decentralised or distributed.

## Open By Default

From this point forward, code that is developed by or for ENTITY_NAME shall be free/open source by default. Detailed requirements follow but at a high level:

* Entities shall develop in the open wherever possible.

* When releasing code, agencies shall ensure that an appropriate FOSS license is applied.

* When procuring the development of code, entities shall ensure that they secure copyright to and delivery of the code in order to facilitate releasing it as open source. 

### Participate in the Open Source Community.

Wherever possible, contributions should be made to existing projects rather than creating independent efforts and all contributions should be given back to the community. 

### Accounts

Civil servants are permitted to attach their name to their contributions and be recognized individually, while the copyright remains with ENTITY_NAME and under the license selected for the project. 

Civil servants are not prohibited from working on side-projects when off duty, and their professional contributions should be distinguished from personal contributions. Criteria are given in the next section.

This distinction should be made through the email address used to submit code:

* Professional contributions should be submitted :

    * with the government email address for civil servants

    * with the company email address for subcontractors

* Personal contributions should be submitted with the personal email address.

Anonymous / generic email contribution should be avoided: managers with civil servants who do not want to release their code should use their own email address instead. 

In addition, civil servants whose employment is sensitive information are to be given cover identities to enable them to contribute to FOSS projects without endangering their safety; equally, contractor employees who have a legal right to keep the fact of their employment non-public and wish to do so must adopt a pseudonym for contributing to ENTITY_NAME projects. In these cases, the same identity must be used by the contributor for all ENTITY_NAME projects to facilitate communications with external developers.

### Professional contribution

Is presumed to belong to ENTITY_NAME, any software designed / created / developed by a civil servant or subcontractor:

	

* during his working period; and/or

* using technical means provided by the Entity ; and/or	

* designed / created / developed following instructions given by the Entity; and /or

* directly or indirectly related to project supported in part or in whole by the organization; and/or

* linkable to an inventive step in the course of the collaborator professional activity for the organization; and/or

* which design / creation / development is part of the purpose of the organization.

Works designed / created / developed outside working hours are affected by these rules.

When a collaborator designs / creates / develops a work filling one or more of these conditions, and contributes this work to a project, it is in fact the Entity which designs / creates / develops and contributes said work to the project.  

### Personal work

Contribution by a civil servant is considered as private and personal if it fulfills all of the cumulative conditions hereafter:

1. it has been designed / created / developed out of working periods, without using any means provided by the Entity ; AND

2. it is not designed / created / developed upon direct nor indirect instructions by the Entity ; AND

3. it cannot be linked to a project directly or indirectly supported in part or in whole by the Entity; AND

4. it is not linkable to an inventive step in the course of the collaborator professional activity for the Entity ; AND

5. its design / creation / development is not part of the purpose of the Entity..

In cases where a civil servant is unsure whether their personal contributions meet these criteria they can consult with  ENTITY_SUPPORT_EMAIL.

Subcontractors should refer to their employer policy.

### Support

ENTITY_NAME will provide a centralized support for cases not covered by this policy or questions others may have to implement the policy through ENTITY_SUPPORT_EMAIL. 

## Contributing to Existing Open Source Projects

ENTITY_NAME’s civil servants and subcontractors are authorized to contribute code and documentation related to FOSS projects that they are using as part of their mission for ENTITY_NAME under the licenses used by these projects, provided that the following conditions are met.

### Evaluate the Project License

ENTITY_NAME’s civil servants and subcontractors can only contribute to projects that have a clearly defined license that is approved by ENTITY_NAME and available at ACCEPTED_LICENSES_URL. 

This consideration should also apply to the dependencies used by the projects:

Shouldn’t one or more of a project’s dependencies fit these criteria, participation in the project may still be appropriate, but further scrutiny and evaluation is needed. Projects falling under this situation should be treated on a case by case basis. Additional support can be obtained through ENTITY_SUPPORT_EMAIL

### Verifying the integrity of the contribution

ENTITY_NAME’s civil servants and subcontractors must be the original authors of the contribution that they submit. If the proposed contribution is in part or entirely derived from a third party work, they must ensure that this party’s work has been licenced in a way that makes it allowed for inclusion in the target project. They must also ensure to follow the required modalities attached to the third party work. 

### Signing Contributor’s License Agreements

ENTITY_NAME’s civil servants and subcontractors may only contribute to projects that require a Contributor’s License Agreement (CLA) that have been agreed upon by ENTITY_NAME and are available at ENTITY_CLA_URL.

Similarly, Individual Contributor’s License Agreements need to be approved by ENTITY_SUPPORT_EMAIL.

## Releasing and Managing Open Source Projects 

### Initial check

Before starting a new project, civil servants shall verify that there is no existing FOSS project that more or less suits the needs (functional requirements, license…) of ENTITY_NAME. 

The proposed project name shall be checked against trademark protection by a third party or whether the name is already used by another Open Source project. 

### Governance

At least two maintainers having full commit rights on a project (preferably from different institutions) should be identified.

### Licenses

Whenever possible, the new project shall use an outbound license ensuring compatibility with corresponding FOSS projects ecosystem.

Any new FOSS project dependency shall be duly checked against its compatibility between the licenses of the various components of the project, including the target licence of the project’s code base.

If the ecosystem is completely new, following licenses are recommended depending on the use cases:

* General use case : a permissive license (default Apache 2.0) to avoid any competition bias and allow private actors to include the software in proprietary code

* Services aimed directly at citizens: a reciprocal license (default GPL v3.0) to ensure contributions will directly benefit the citizens

Creating a new license is very strongly discouraged and explicit approval is required from ENTITY_SUPPORT_EMAIL.

Contributions should be accepted under the same license as the project outbound license. A CLA should not be required for the project. Instead, a process like the [Developer’s Certificate of Origin](http://developercertificate.org/) (DCO), can be used to verify that developers agree with the project’s license, if so desired.

### Version control system

Releasing the source code can be made on any public distributed version control system (git or mercurial) or corresponding hosted platform . A copy of the public repository should be synced with the ENTITY_NAME version control system for backup and integrity checks.

### Security

ENTITY_NAME’s standard security process should be applied.

### Deprecation Policy

Public repositories are archived in a manner accessible to the public when ENTITY_NAME hands over or discontinues a software project.

