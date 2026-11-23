# OpenChain Telco SBOM Guide Version 1.2

## 1. Scope

This document “OpenChain Telco SBOM Guide” aims to outline certain requirements related to how an entity creates, delivers, and consumes Software Bill of Materials (SBOM), so that entities that produce and/or consume SBOMs that conform to this guide can ensure repeatability and streamlining of tools and processes for generating and consuming SBOMs. *Please Note* that this guide does not require a conforming entity to adopt OpenChain (in any version) but doing so is greatly encouraged.

This guide is designed to work on a per SBOM level: an entity can use it as its sole way of delivering SBOMs, but it is the individual SBOM that the guide refers to, not the entity that provides the SBOM. An SBOM using this guide can be called “OpenChain Telco SBOM Guide Compatible.”

Releasing SBOMs that match the requirements outlined in this guide does not preclude an entity from also delivering SBOMs for the same software in alternate ways or formats.

This guide is licensed under [Creative Commons Attribution License 4.0 (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/).

In release 1.0 and 1.1 of this Guide, only SPDX 2.2 and 2.3 were allowed.
So, we used the SPDX 2 tag:value field names to express the mandatory and recommended fields.
We now allow also SPDX 3.0.1. Consequently, we now use the 2026 CISA Minimum Elements field names and provide the mapping in SPDX 2 and SPDX 3.

## 2. Terms and definitions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
      NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED",
      "MAY", and "OPTIONAL" in this document are to be interpreted as
      described in BCP 14 [[RFC2119]](https://www.ietf.org/rfc/rfc2119.txt)  [[RFC8174]](https://www.ietf.org/rfc/rfc8174.txt) when, and only when, they
      appear in all capitals, as shown here.

### Data Format
Data Format means the data format of the information in the SBOM. Possible Data Formats include SPDX, CycloneDX, SWID, or other proprietary formats.

### Entity
Entity shall mean the legal entity (for profit, non-profit, or natural person) that distributes software to third parties (e.g., other organizations or individuals). Entity does not include other group companies, or companies under common control of the Entity.

### SBOM
A Software Bill of Materials (SBOM) is a formal record containing the details and supply chain relationships of various components used in building software.

### SBOM Type
An SBOM can be of one of the following types:
* Design,
* Source,
* Build,
* Analyzed,
* Deployed,
* Runtime.

The definition of these types can be found in the
[CISA document](https://www.cisa.gov/sites/default/files/2023-04/sbom-types-document-508c.pdf).

The 2026 CISA Minimum Elements document uses "Before build", "Build" and "After build".

"Before build" can be mapped to "Design" or "Source".

"After build" can be mapped to "Analyzed", "Deployed" or "Runtime".

### SPDX
SPDX (Software Package Data Exchange) is the [ISO standard](https://www.iso.org/standard/81870.html) (ISO/IEC 5962:2021) for exchanging SBOM for a given software package, including associated license and copyright information. The standard was created by the [Linux Foundation's SPDX project](https://spdx.dev/).

The current ISO standard describes SPDX 2.2.1. Revision 2.3 of the standard exists but was not sent to ISO.
Revision 2.3.1 includes in annex L the mapping of the 2026 CISA Minimum Elements in SPDX.

Revision 3.0.1 of SPDX was sent to ISO and will be published soon. The acronym SPDX now means System Package Data Exchange.

### OpenChain
OpenChain means [OpenChain ISO/IEC 5230:2020](https://www.iso.org/standard/81039.html), the international standard that specifies the key requirements of a quality open source license compliance program in order to provide a benchmark that builds trust between organizations exchanging software solutions that incorporate open source software. The OpenChain standard is produced by the [OpenChain project](https://www.openchainproject.org) of the Linux Foundation.

### Transitive dependencies
Transitive dependencies are all components that are necessary for the software to run. They include any dependency of the package that is not a direct dependency.

### Package-URL (PURL)
Package-URL (PURL) is an [ECMA standard](https://tc54.org/purl/) to uniquely identify software packages.
It will become an ISO standard.

## 3. Requirements

### 3.1 Data Format
An OpenChain Telco SBOM Guide compatible document SHALL adhere to:
* the version 2.2 of the SPDX Data Format as standardized in ISO/IEC 5962:2021,
* or to the version 2.3 of SPDX,
* or to version 3.0.1 of SPDX and as further described below with respect to the included elements.

#### 3.1.1 Verification and reference material
* ISO/IEC 5962:2021 Information technology — SPDX® Specification V2.2.1
* [SPDX Specification V2.3](https://spdx.github.io/spdx-spec/v2.3/)
* [SPDX Specification V3.0.1](https://spdx.github.io/spdx-spec/v3.0.1/)

#### 3.1.2 Rationale
To ensure simplified handling and streamlining of tooling and competences in the telecommunications supply chain, both for suppliers and consumers of software, OpenChain Telco SBOM Guide Compatible documents shall adhere to the SPDX Data Format as standardized in ISO/IEC 5962:2021. By harmonizing on the use of this standard SBOM Data Format in an organization's external interfaces, the complexities for organizations supplying and consuming software are simplified, as only one set of unified requirements will be applicable.

As clarification, an entity is free to use alternative Data Formats for internal use or deliver SBOMs in alternative Data Formats to organizations that so request or on its own initiative. The OpenChain Telco SBOM Guide is a SBOM-level specification to adhere to, and not an organizational specification to adhere to. There are no conforming entities, only conforming SBOMs, delivered by entities that have implemented the OpenChain Telco SBOM Guide.

### 3.2 SPDX Elements to be included in an OpenChain Telco SBOM Guide Compatible document

The following elements are REQUIRED.

**SBOM Metadata**

| Element                  | SPDX 2.2 and 2.3                       | SPDX 3.0.1                         |                 |
| ------------------------ | -------------------------------------- | ---------------------------------- | --------------  |
| SBOM Author              | Creator                                | CreationInfo.createdBy             |                 |
| SBOM Author Signature    | _see below_                            | _see below_                        |                 |
| SBOM Data Format Name    | SPDXVersion ("SPDX-2.2" or "SPDX-2.3") | _implicit_                         |                 |
| SBOM Data Format Version | SPDXVersion ("SPDX-2.2" or "SPDX-2.3") | CreationInfo.specVersion ("3.0.1") |                 |
| SBOM Generation Context  | CreatorComment (see below)             | software_Sbom.sbomType             |                 |
| SBOM Timestamp           | creationInfo.created                   | CreationInfo.created               |                 |
| SBOM Tool Name           | creationInfo.creators                  | CreationInfo.createdUsing          | See section 3.6 |
| SBOM Tool Version        | creationInfo.creators                  | CreationInfo.createdUsing          | See section 3.6 |
| SBOM Version             | documentNamespace                      | SBOM.spdxId                        |                 |

There is no native field to express the SBOM Version in SPDX 2.2, 2.3 and 3.0.1.

As a workaround, we can use:
* `documentNamespace` in SPDX 2.2 and 2.3;
* SBOM.spdxId in SPDX 3.0.1 and optionally relationship `amendedBy` to previous SBOM.spdxId.

There is no native field to express the SBOM Author Signature in SPDX 2.2, 2.3 and 3.0.1. It is MANDATORY to use an external signed envelope.

The following element is REQUIRED for an SBOM in SPDX 2.2 and 2.3:
* CreatorComment: to be able to put “SBOM Build information”

**Package information**

| Element                                 | SPDX 2.2 and 2.3                       | SPDX 3.0.1                         |
| --------------------------------------- | -------------------------------------- | ---------------------------------- |
| Component Name                          | PackageName                            | software_Package.name              |
| Component Version                       | PackageVersion                         | packageVersion                     |
| Component Identifiers                   | ExternalRef (see below)                | packageUrl                         |
| Component Hash Value                    | PackageChecksum or PackageVerificationCode (see below) | verifiedUsing      |
| Component Hash Algorithm                | PackageChecksum or SHA1 (if PackageVerificationCode)  | Hash.algorithm      |
| Component Producer (was Supplier Name)  | PackageSupplier (or PackageOriginator) | suppliedBy (or originatedBy)       |
| Component License                       | PackageLicenseConcluded or/and PackageLicenseDeclared | Relationships hasConcludedLicense or/and hasDeclaredLicense |
| Component Dependency Relationship       | Relationship: DESCRIBES, CONTAINS, DEPENDS_ON         | Relationship: describes, contains, dependsOn            |

The following elements are REQUIRED (but they might be `NOASSERTION` or `NONE`):
* `PackageDownloadLocation`: mandatory in SPDX 2.2 and 2.3
* `PackageCopyrightText`: mandatory in SPDX 2.2

`PackageDownloadLocation` SHOULD not be `NOASSERTION` or `NONE` for publicly downloadable packages.
For packages without a public download location, like commercial packages, as well as any open source packages that are no longer hosted publicly or that are provided directly by a supplier from a location the SBOM recipient cannot access, it SHOULD be `NONE`.
If the existence of the download location is unknown, it SHOULD be `NOASSERTION`.

In SPDX 2.2 and 2.3:
* One of the two attributes `PackageChecksum` or `PackageVerificationCode` is MANDATORY: implements the Component Hash from “CISA SBOM Minimum elements”.

In SPDX 3:
* `Software/Package.verifiedUsing` is MANDATORY: implements the Component Hash from “CISA SBOM Minimum elements”.

At least one of `PackageLicenseConcluded` and `PackageLicenseDeclared` MUST NOT be `NOASSERTION`.

A package SHOULD be identified by a Package-URL (PURL).

If the PURL is present, in SPDX 2.2 and 2.3, it MUST be put in `ExternalRef` field, e.g.
```
ExternalRef: PACKAGE-MANAGER purl pkg:pypi/django@1.11.1
```

If the PURL is present, in SPDX 3.0.1, it MUST be put in `packageUrl` property
(https://spdx.github.io/spdx-spec/v3.0.1/model/Software/Properties/packageUrl/)

Component Dependency Relationship

* “NTIA SBOM Minimum Elements” mandate at least DESCRIBES and CONTAINS (Dependency Relationship)
* “CISA SBOM Minimum Elements” mandate at least DEPENDS_ON (Dependency Relationship)

At least one of DESCRIBES, CONTAINS and DEPENDS_ON MUST be present for each package.

#### 3.2.1 Verification and reference material
NTIA Minimum Elements

2026 CISA Minimum Elements

CISA "SBOM Author Signature" cannot be represented in SPDX 2 or SPDX 3. It MUST be provided using an external file.

CISA "SBOM Data Format Name" has no specific field in SPDX 3, it is implicit.

#### 3.2.2 Rationale
Recognizing the Telco industry need for harmonization and special requirements, the “OpenChain Telco SBOM Guide” is proposed to ensure predictability to the industry as to the elements of an SBOM that is expected.

In SPDX 2.2 and 2.3, it maps to `PackageChecksum` or `PackageVerificationCode`.
Most SCA tools have the capability to produce hashes.

The CISA document "Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM), Third Edition"
https://www.cisa.gov/resources-tools/resources/framing-software-component-transparency-2024
allows both, see table in section 2.5.

2026 CISA Minimum Elements require License.
In versions 1.0 and 1.1 of the Guide, PackageLicenseConcluded and PackageLicenseDeclared were mandatory,
but could be NOASSERTION. In order to comply with 2026 CISA Minimum Elements, at least one of them must contain a real license
(either from the SPDX license list or a custom license).

Package-URL (PURL) is a _de facto_ standard to uniquely identify software packages. It is also an ECMA standard.

### 3.3 Machine Readable Data Format
An OpenChain Telco SBOM Compatible document SHALL include, at a minimum, the SPDX in one of the following machine-readable formats:
* Tag:Value or JSON in SPDX 2.2 or 2.3,
* JSON in SPDX 3.0.1.

In SPDX 3.0.1, the format SHALL be JSON (more precisely JSON-LD).

#### 3.3.1 Verification and reference material
Tag:Value and JSON formats are described here:
* in SPDX 2.2 https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* in SPDX 2.3 https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

#### 3.3.2 Rationale
There are 3 major formats for SBOMs: SPDX, CycloneDX, and SWID.
These 3 formats are the ones recommended by NTIA document "The Minimum Elements For a Software Bill of Materials (SBOM)" (see References section).

The reasons for selecting SPDX as data format of the OpenChain Telco SBOM Guide include the following:
* SPDX is an ISO standard,
* SPDX has more features than CycloneDX for license compliance,
* SPDX has a human-readable format (CycloneDX has only JSON and XML),
* SWID is more a software identifier than a fully-fledged SBOM format; 2026 CISA Minimum Elements has removed SWID from list of data formats.

To facilitate a simplified toolchain, a machine-readable version of the SBOM needs to be included. To ensure repeatability and harmonization a conformant SBOM must be in Tag:Value or JSON format. An entity can release additional machine-readable formats but they are not required to conform to the Guide.

Tag:Value is the most human-readable format, and there are converters between the various SPDX formats
(e.g. https://tools.spdx.org/app/convert/). JSON is a format produced by several tools.

### 3.4 Human Readable Data Format
An OpenChain Telco SBOM Compatible document SHALL include, at a minimum, the SPDX in one of the following human-readable formats:
* Tag:Value or JSON in SPDX 2.2 or 2.3,
* JSON in SPDX 3.0.1.

#### 3.4.1 Verification and reference material
Tag:Value and JSON formats are described here:
* in SPDX 2.2 https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* in SPDX 2.3 https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

#### 3.4.2 Rationale
As the Tag:Value format is also human-readable it has been chosen so that both the requirements for a standardized machine-readable and human-readable version can be met using one file. An entity can release additional human-readable formats, but they are not required to conform to the OpenChain Telco SBOM Guide.

### 3.5 File name

In SPDX 2.2 and 2.3, in Tag:Value format the file name SHOULD end with ```.spdx```.

In SPDX 2.2 and 2.3, in JSON format, the file name MUST end with ```.json```, it SHOULD end with ```.spdx.json```.

In SPDX 3.0.1, the file name MUST end with ```.json``` or ```.jsonld```, it SHOULD end with ```.spdx3.json```.

#### 3.5.1 Verification and reference material

SPDX 2:
* https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

SPDX 3:
* https://github.com/spdx/spdx-spec/blob/develop/docs/serializations.md (File naming section)

#### 3.5.2 Rationale

This is the recommended naming from the SPDX standard.

### 3.6 SBOM Build information
SBOMs conforming to the OpenChain Telco SBOM Guide MUST contain information as when they were created and to which version of the software they were created.

In SPDX 2.2 and 2.3:

The `Created` field MUST contain the time when the SBOM was created.

The `CreatorComment` field MUST contain the version of the software.

The `Creator` field MUST:
* contain a line with the `Organization` keyword;
* contain a line with the `Tool` keyword; in this line we MUST have after the `Tool` keyword the tool name and the tool version.

The tool name and the tool version SHOULD be separated by hyphen ("-"), no other hyphen SHOULD appear on the line.

SBOMs conforming to the OpenChain Telco SBOM Guide MUST provide their SBOM Types as
[defined by CISA](https://www.cisa.gov/sites/default/files/2023-04/sbom-types-document-508c.pdf).

As SPDX 2 has no specific field, in SPDX 2 the SBOM Types MUST be put in the `CreatorComment` field.

The SBOM Type RECOMMENDED syntax is “SBOM Type: xxx” where “xxx” is one of the 6 keywords “Design”, “Source”, “Build”, “Analyzed”, “Deployed” and “Runtime”.

In SPDX 3:
* CreationInfo.createdBy MUST point to a field of type "Organization",
* CreationInfo.createdUsing MUST point to a field of type "Tool",
* CreationInfo.created MUST contain the time when the SBOM was created,
* the software version MUST be put in the `software_packageVersion` property,
* the SBOM types MUST be put in the `sbomType` property.

#### 3.6.1 Verification and reference material
SPDX standards

#### 3.6.2 Rationale
It is important to know which tool and which version of the tool have created the SBOM.

The SPDX 2.2 and 2.3 standards give "toolidentifier-version" as an example, but it is not mandatory to have this syntax.

For example, there is a tool that outputs:
```
Creator: Tool: sigs.k8s.io/bom/pkg/spdx
```
We have also:
```
Creator: Tool: scancode-toolkit 32.3.0
```
and
```
Creator: Tool: SCANOSS-PY: 1.18.1
```
where the name contains a hyphen, and the tool name and tool version are not separated by a hyphen.

So, we cannot require a precise syntax.

The `CreatorComment` is a free text field. We use it to store the CISA SBOM Types, as there is no
specific field for that in SPDX 2.2 and 2.3, but any other information can of course be put in it also.

We do not require a specific format. We only require that at least one of the words
“Design”, “Source”, “Build”, “Analyzed”, “Deployed”, “Runtime” is present, regardless of the case.

So, the following possibilities are all valid, and the first one is the recommended one:
```
CreatorComment: SBOM Type: Deployed
```
```
CreatorComment: Analyzed
```
```
CreatorComment: This SBOM was created during build phase.
```

### 3.7 Timing of SBOM delivery
The SBOM SHALL be delivered no later than at the time of the delivery of the software (in either binary or source form). 

#### 3.7.1 Verification and reference material
“NTIA SBOM Minimum elements”, section “Distribution and Delivery”

#### 3.7.2 Rationale
To ensure that the receiving entity can ingest the software and its SBOM, it shall be delivered no later than at the delivery of the software. An SBOM may be delivered before the software if an adopting entity so elects, but the software delivery must nevertheless be accompanied by the corresponding SBOM to ensure compliance with the Guide.

### 3.8 Method of SBOM delivery
The SBOM SHALL be embedded into the software “package” where technically feasible. If it is not technically feasible to embed the SBOM into the software “package” being delivered, such as in the case of space-constrained embedded systems, the supplying party will supply a web hosted version of the SBOM that is available for at least 18 months and SHALL NOT in any way restrict recipients’ ability to copy and store these locally for their own use. Such restrictions MAY NOT be placed on the recipient in additional confidentiality agreements. 

#### 3.8.1 Verification and reference material
“NTIA SBOM Minimum elements”, section “Distribution and Delivery”

#### 3.8.2 Rationale
Other options of SBOM delivery such as webhosting are less stable and access is not guaranteed over time; however, “embedding” may not be technically feasible. Thus, in scenarios where it is not possible on technical grounds to include the SBOM in the software delivery, publishing the SBOM online is permitted provided that the SBOM is accessible for the recipients of the software for 18 months. This duration is in line with the OpenChain specification requirements on recertification.

### 3.9 Encryption and storage of SBOM
SBOM providers SHALL use encryption to protect the confidentiality of an OpenChain Telco SBOM Compatible document. The encryption used SHALL protect the integrity, authenticity, and confidentiality of the document at rest and during transport using best practices. The key(s) used for the encryption of the data SHALL be protected by all parties in an agreed upon manner. While at rest the keys, the encrypted SBOM, the unencrypted SBOM, or parts of the SBOM, SHALL be subject to access control where only designated individuals within the receiving organization have the necessary rights to read it. Any additional protection mechanisms that are required for the storage of the SBOM SHALL be agreed upon by both parties.

The provider of the Software may choose to make an SBOM available for the public. This guide does not prevent such actions, however the above, 3.9 requirement still applies to the SBOM that is to be shipped with the product according to section 3.8 of this guide.

### 3.9.1 Verification and reference material

### 3.9.2 Rationale
The security, confidentiality, and integrity of the SBOM and the information contained therein may be of great concern and important for both the provider and the consumer of an SBOM, thus adequate measures must be taken to ensure that it is protected by all parties.

### 3.10 SBOM Scope
The SBOM SHALL contain all open source software that is delivered with the product including all of transitive dependencies. The SBOM SHOULD contain all commercial components.

If some components are not included, they MUST be reported as “known unknowns.”

#### 3.10.1 Verification and reference material
“NTIA SBOM Minimum elements”, section “Known Unknowns”

#### 3.10.2 Rationale
It might not be possible, advisable or feasible to have the commercial component information in the SBOM. However, it is advisable that the SBOM should be as complete as possible.

### 3.11 SBOM in a SaaS deployment
As the OpenChain Telco SBOM Guide is only applied on the SBOM level, there is no requirement on an entity that has elected to supply an OpenChain Telco SBOM Compatible document for some or even all its software deliveries to also provide this for its SaaS offerings. However, an entity may elect to apply the OpenChain Telco SBOM Guide also to its SaaS offerings and thus also deliver the open source software used in the SaaS offerings with their transitive dependencies as an SBOM.

#### 3.11.1 Verification and reference material

#### 3.11.2 Rationale
There is currently no consensus in the industry on what an SaaS SBOM should contain.

### 3.12 SBOMs for containers
SBOMs for containers SHOULD include all open source components delivered in the container. This includes the packages installed into the container, components copied or downloaded to the container and dependencies used to build the compiled components in the container.

#### 3.12.1 Verification and reference material

#### 3.12.2 Rationale
Every open source component delivered should be part of the SBOMs.

### 3.13 SBOM Verification
It is RECOMMENDED to provide a digital signature of the SBOM in order to guarantee the
integrity of the SBOM.

#### 3.13.1 Verification and reference material
Sigstore https://www.sigstore.dev/ is an example of such capability.

#### 3.13.2 Rationale
While the verification of SBOMs is an important topic, OpenChain Telco defers this work to other initiatives for the moment and intends to revisit this topic in future iterations of this document.

### 3.14 SBOM Merger
SBOMs following this Guide can be built from several SBOM files with a well-defined relationship to each other using the relationship definition features in SPDX.

#### 3.14.1 Verification and reference material
There exist tools to merge several SBOMs into one, e.g. https://github.com/interlynk-io/sbomasm

#### 3.14.2 Rationale
It is often easier when dealing with a large software product to provide individual SBOMs of its parts than a single SBOM.

### 3.15 SBOM Confidentiality
SBOMs MAY be subject to confidentiality agreements. A conformant SBOM MUST NOT, however, be subject to any confidentiality agreements that would prevent a recipient from redistributing the parts of the SBOM applicable to software that such recipient has a right to redistribute.

#### 3.15.1 Verification and reference material
“NTIA SBOM Minimum elements”, section “Access Control”

#### 3.15.2 Rationale
Some open source software licenses enable any recipient to redistribute the software. In these situations, the recipients should also be able to redistribute the relevant parts of the SBOMs.

## 4. Conformant notice
To indicate that the software has a conformant SBOM available, you MAY use the following statement: “This software is supplied with an SBOM conformant to the OpenChain Telco SBOM Guide v1.2, the Guide is available at [https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md)”

You MAY at your choosing use the following statement in your Telco Guide conformant SBOM “This SBOM conforms to the OpenChain Telco SBOM Guide v1.2 [https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md), it is provided to the recipient free of charge, and the recipient is free to redistribute this SBOM to any third party that they distribute the corresponding software to, provided that they have all the necessary rights to distribute the software to such third party”

The following statement MAY be used as statement in the RFP document, order document, or contract document when requesting an RFP, purchasing orders, or outsourced development orders from a software vendor or telco system suppliers.
“When releasing software, it is REQUIRED to provide an SBOM compliant with the OpenChain Telco SBOM Guide v1.2 for all software released.  This Guide is available at [https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md)”

## 5. References

* SPDX (ISO/IEC 5962:2021)
  * https://spdx.dev/
  * https://www.iso.org/standard/81870.html
  * https://standards.iso.org/ittf/PubliclyAvailableStandards/c081870_ISO_IEC_5962_2021(E).zip
  * SPDX Specification V2.3: https://spdx.github.io/spdx-spec/v2.3/
  * SPDX Specification V3.0.1: https://spdx.github.io/spdx-spec/v3.0.1/
* OpenChain (ISO/IEC 5230:2020)
  * https://www.openchainproject.org/
  * https://www.iso.org/standard/81039.html
  * https://standards.iso.org/ittf/PubliclyAvailableStandards/c081039_ISO_IEC_5230_2020(E).zip
* The Minimum Elements For a Software Bill of Materials (SBOM) a.k.a. “NTIA Minimum Elements”
  * https://www.ntia.doc.gov/report/2021/minimum-elements-software-bill-materials-sbom
* 2026 Minimum Elements for a Software Bill of Materials (SBOM)
  * https://www.cisa.gov/sites/default/files/2026-07/2026_cisa_sbom_minimum_elements_508c.pdf
* Framing Software Component Transparency: Establishing a Common Software Bill of Materials (SBOM), Third Edition
  * https://www.cisa.gov/resources-tools/resources/framing-software-component-transparency-2024
* Package-URL (PURL)
  * https://github.com/package-url/purl-spec
  * ECMA standard: https://tc54.org/purl/

## 6. Guide history

The following updates of the Guide have been made in version 1.1.

* Both PackageChecksum and PackageVerificationCode are allowed as package hash.
* The package hash is RECOMMENDED instead of MANDATORY.
* ExternalRef is RECOMMENDED instead of MANDATORY.
* FilesAnalyzed is no longer MANDATORY.
* Examples are provided for the CISA SBOM Types.
* A RECOMMENDED syntax is given for CISA SBOM Types.
* sbomasm is a better example of SBOM merge tool.
* Add reference to new CISA document.

An SBOM that conforms to version 1.0 of the Guide will also conform to version 1.1 of the Guide.
The reverse is not true.

The following updates of the Guide have been made in version 1.2.

* Allow SPDX 3 as a possible format for an OpenChain Telco SBOM.
* Add a recommendation on file naming.
* Add a section about "Encryption and storage of SBOM".
* Add the fact that the Guide complies with the 2026 CISA Minimum Elements.
* PackageLicenseConcluded and PackageLicenseDeclared cannot be both NOASSERTION.
* Add the fact that Package-URL is now an ECMA standard.
