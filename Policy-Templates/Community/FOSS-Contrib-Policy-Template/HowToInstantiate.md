# How To Use These Templates

Instantiating this policy requires explicit preliminary work described in this section:

Below is a list of all <FIELDS> that need to be filled to instantiate the policy:

* ENTITY_NAME : correspond to the public entity name

* ENTITY_SUPPORT_EMAIL : email address that will provide support and can update the instantiate policy

* ENTITY_CLA_URL : URL of all preapproved contributor’s license agreement signed

* ACCEPTED_LICENSES_URL : URL of all accepted FOSS licenses

It is strongly encouraged that you provide assistance around this policy by providing an email address or service desk under<ENTITY SUPPORT EMAIL>

### Scope

Including subcontractors in the scope might require additional verification and contractual clauses to public tenders.

### Open By Default

This is an optional clause: In order to accomplish this, departments and agencies shall establish technical and acquisitions capabilities to do so in an efficient and consistent manner, and shall establish transparent processes where exceptions are needed.

### Contributing to existing projects

Subcontractors contracted to develop parts or the entirety of the contribution of ENTITY_NAME to a FOSS project, shall, by the terms of their contract(s) with ENTITY_NAME, authorize their contribution to the FOSS project.

### Licenses

ENTITY_NAME should maintain and publish a list of accepted FOSS licenses among the FSF / OSI approved ones at the ACCEPTED_LICENSES_URL. 

Another option would be to rely on those institutions and accept all FSF / OSI approved licenses.

Guidance should be provided on ENTITY_NAME use cases and corresponding software developped.

### Signing Contributor’s License Agreements

Some existing projects require a Contributor’s License Agreement (CLA) to be signed in order to be able to accept contributions to the project. The entity will review and accept corporate CLA, as long as:

* the license for the project is a FSF/OSI approved license

* the CLA does not prohibit the participation of a government employee

* the CLA does not prohibit the reuse of the contribution by the government employing the official

* the CLA does not extend beyond the boundaries of the contributions into other works of the contributor

The list of acceptable project CLAs must be filled out by the Entity after review and acceptance by your legal council.

Some project require in addition to corporate CLA, individual CLA for maintainer role. In that case, the entity should review and track all civil servants with commit rights to existing projects requiring such CLA.

### Version control system

Entities shall select a version control system for use in both internal development and publication of code. Going forward all code development by your entity must use a version control system.

There are a number of version control systems available that may be appropriate to meet needs of your entity. In choosing a version control system adhere to the following principles:

* Entities should adopt a single version control system wherever possible

* Entities should use a distributed version control system wherever possible

* Entities should use a version control system which itself is Free/Open Source software. 

* Entities should err on the side of adopting a standard platform with the communities they work most closely with as well as their peers.

* The system must be interoperable with [git](https://git-scm.com/). Interoperability with this open standard is crucial to your agency's ability to collaborate with other agencies and the open source community and will greatly ease future platform integrations and migrations.

* If your entity needs both private and public repositories, does the system allow seamless integration between the two?

In order to facilitate contribution from a wide range of developers, repositories for new projects developed by your public administration should be primarily hosted on a public version control system. To mitigate risks, the agency should periodically obtain a copy of the repository but development should take place on the public repository.

[In addition, some public administrations provide their own platforms, most notably Joinup (https://joinup.ec.europa.eu) by the European Commission and Code.gov (https://code.gov) by the US government.](https://bitbucket.org/)

To engage the open source community your entity may want to consider the social features of the system beyond version control, such as a ticketing system, a wiki or an automated build system. 

### Applicability of Legal Principles Reflected in the Policy

Some of the principles expressed in the policy for ownership and transfer of copyright and the resulting acquisition processes may not be applicable in any particular legal environment by default. Hence, entities should contractually bound their subcontractors and employees to their FOSS Contribution Policies.

