# SBOM Quality Guide

## Table of Contents

1. [Introduction](#1-introduction)  
2. [Objectives and Scope](#2-objectives-and-scope)  
3. [Terms and Definitions](#3-terms-and-definitions)  
4. [Basic Requirements](#4-basic-requirements)  
5. [SBOM Quality Assessment and Improvement Measures](#5-sbom-quality-assessment-and-improvement-measures)  
 5.1 [Ensuring Accurate and Consistent Information Descriptions](#51-ensuring-accurate-and-consistent-information-descriptions)  
 5.2 [Standardization and Normalization of Component Granularity](#52-standardization-and-normalization-of-component-granularity)  
 5.3 [Complementing Source Information and Enhancing Transparency](#53-complementing-source-information-and-enhancing-transparency)  
 5.4 [Strengthening Vulnerability Integration and Risk Management](#54-strengthening-vulnerability-integration-and-risk-management)  
 5.5 [Enhanced Information Integration and Collaboration Between Upstream and Downstream](#55-enhanced-information-integration-and-collaboration-between-upstream-and-downstream)  
 5.6 [Establishing a Tamper Detection and Change Management System](#56-establishing-a-tamper-detection-and-change-management-system)  
 5.7 [Clarifying the Scope of Descriptions and Defining Accountability](#57-clarifying-the-scope-of-descriptions-and-defining-accountability)  
 5.8 [Unified Expression of Inter-Component Relationships](#58-unified-expression-of-inter-component-relationships)  
6. [Automation Strategy and Operational Process](#6-automation-strategy-and-operational-process)  
 6.1 [Implementation of Automated Verification Tools](#61-implementation-of-automated-verification-tools)  
 6.2 [Conversion Processes and Normalization](#62-conversion-processes-and-normalization)  
 6.3 [Reducing Operational Burdens and Integrating Manual Reviews](#63-reducing-operational-burdens-and-integrating-manual-reviews)  
7. [Guide Management and Administration](#7-guide-management-and-administration)  
 7.1 [Guide Update Process](#71-guide-update-process)  
 7.2 [Change History Management and Documentation](#72-change-history-management-and-documentation)  
8. [References and Related Materials](#8-references-and-related-materials)

#### Appendix-1. [SBOM Sample](#appendix-1-sbom-sample)  
#### Appendix-2. [Template for Chapter 5 Items](#appendix-2-template-for-chapter-5-items)

---

### Introduction  

This section explains the background that demands an improvement in SBOM quality, as well as the significance of creating this guide. While following the basic framework of the OpenChain-Telco-SBOM-Guide, it integrates challenges raised in recent industry discussions to provide guidelines for producing SBOMs with transparency and consistency.

## Chapter Summaries

### 1. Objectives and Scope  
This chapter inherits the [1. Scope from OpenChain Telco SBOM Guide Version 1.1](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md).  
It may be extended, reduced, or modified as necessary to suit industry-independent and format-agnostic formats. The detailed breakdown of this guide is intended to support usage across various industries and formats.

- **Objective**: To present improvement measures that enhance standardization, accuracy, transparency, and automation potential of SBOMs while fostering a common understanding among stakeholders.  
- **Scope**: Applies to processes relating to SBOM creation and operation for software packages, containers, SaaS, embedded software, and other relevant targets.

### 2. Terms and Definitions  
This chapter inherits the [2. Terms and definitions from OpenChain Telco SBOM Guide Version 1.1](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md#2-terms-and-definitions) to standardize specialized terminology used within this guide, such as SBOM, SPDX, **CycloneDX**, purl, and dependency relations, in order to prevent confusion and misinterpretation.

### 3. Basic Requirements  
This chapter inherits the [3. Requirements from OpenChain Telco SBOM Guide Version 1.1](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md#3-requirements). It lays out the fundamental requirements that must be met.

### 4. SBOM Quality Assessment and Improvement Measures  
This chapter systematically organizes specific check items and resolutions for assessing and improving SBOM quality, based on issues discussed within the OpenChain SBOM SG. This item will be added using the [Appendix 2. Template for Chapter 5 Items](#appendix-2-template-for-chapter-5-items) and finilised after the review.

> **Note: Current items are from discussions within the SBOM subgroup.**  
> Duplicate challenges derived from these discussions have been merged.  
> - [2025/02/03](https://github.com/OpenChain-Project/OpenChain-JWG/blob/master/subgroups/sbom-sg/meetings/20250203.en.md)  
> - [2025/02/17](https://github.com/OpenChain-Project/OpenChain-JWG/blob/master/subgroups/sbom-sg/meetings/20250217.en.md)  
> - [2025/02/25](https://github.com/OpenChain-Project/OpenChain-JWG/blob/master/subgroups/sbom-sg/meetings/20250225.en.md)  
> - [2025/03/05](https://github.com/OpenChain-Project/OpenChain-JWG/blob/master/subgroups/sbom-sg/meetings/20250305.en.md)  
> - [2025/03/24](https://github.com/OpenChain-Project/OpenChain-JWG/blob/master/subgroups/sbom-sg/meetings/20250324.en.md)

#### 4.1 Ensuring Accurate and Consistent Information Descriptions

##### 4.1.1 Overview  
Challenges exist in the inconsistent representation of information such as package names, versions, and supplier names across different companies and tools. Without unified standards, automatic analysis of SBOMs or vulnerability matching becomes challenging, leading to inaccuracies.

##### 4.1.2 Improvement Measures  
- Establish unified representation rules based on industry standards or internal guidelines, and widely share specific examples (such as regular expression format examples).  
- Deploy automated verification tools to check whether package names, versions, and supplier names comply with the established rules.  
- Develop a regular review and feedback process to update the standards and demonstrate continuous improvement.

##### 4.1.3 Evaluation Methods  
- Monitor the number of rule violations quantitatively through automated verification tools, measuring the decrease in errors and inconsistencies before and after improvements.  
- Periodically conduct random checks to assess adherence to unified rules, evaluating the pass rate.  
- Share qualitative feedback on the effect of updates and improvements from various departments and companies.

##### 4.1.4 Risks and Considerations  
- Insufficient configuration of verification tools may result in inadequate handling of exceptional or unique cases.  
- Misalignment between field practices and updated rules or regular expression examples could cause legitimate information to be falsely flagged.  
- While automation is pursued, final review and handling of exceptions must rely on manual checks.

#### 4.2 Standardization and Normalization of Component Granularity  
- Clearly define the granularity of information descriptions (e.g., per file or per package) and organize the methodology for using transformation tools to integrate information across multiple SBOMs.

#### 4.3 Complementing Source Information and Enhancing Transparency  
- Specify essential items such as listing source files, hash values, or license information even when providing binaries, and set policies to adopt automated extraction processes.

#### 4.4 Strengthening Vulnerability Integration and Risk Management  
- Define methods for linking component information with vulnerability data (such as CVE) and introduce automated mapping for risk assessment.  
- Clarify how vulnerability data is incorporated into SBOM entries and determine definitive conclusions.  
- Consider alignment with legal regulations and internal guidelines, recognizing that final confirmation and metadata adjustments require manual verification.  
- While adherence to formats defined by CPE is recommended, practical information from each company might lack some mandatory items or include optional sections with proprietary interpretations.

#### 4.5 Enhanced Information Integration and Collaboration Between Upstream and Downstream  
- Recommend operating a common repository, performing regular cross-checks, and utilizing automated difference comparison tools to ensure consistency between vendor-provided SBOMs and internal SBOMs at the manufacturing site.

#### 4.6 Establishing a Tamper Detection and Change Management System  
- Propose concrete measures such as applying digital signatures or hash values immediately after SBOM generation, keeping detailed change histories, and employing automated monitoring systems to detect tampering.

#### 4.7 Clarifying the Scope of Descriptions and Defining Accountability  
- Clearly outline the range of information to be included in an SBOM (e.g., source code, binary, firmware, hardware information), and explicitly define accountability such as the creator or the package supplier.

#### 4.8 Unified Expression of Inter-Component Relationships  
- Establish uniform rules for describing dependencies and relationships among components (e.g., “dependsOn”, “contains”, “generates”), and specify methods for consistency checks via templates and automated verification tools.

#### 4.9 Capturing Dependencies and Issues in Package Retrieval Methods  
- Recognize that obtaining dependency information from both source code and packages may lead to a mix of redundant or overlapping data, making overall dependency analysis challenging.  
- When analysis relies solely on lock files or package manager logs, the most recent or transitive dependencies may not be fully captured.  
- Identify the need for standardized and automated dependency extraction methods, complemented by manual adjustments when necessary.

#### 4.10 Insufficient Interoperability and Flexibility Among Tools  
- Tools such as ORT (OSS Review Toolkit) may support alternatives (for example, FOSSology instead of the default ScanCode), but practical examples of switching between tools remain scarce. Their interoperability is not widely verified.  
- Documentation or rules to strengthen collaboration among different tools are insufficient, requiring users to adjust based on tool-specific characteristics.

#### 4.11 Tool Maintenance, Update Status, and Community Coordination  
- Some of the tools in use suffer from a shortage of maintainers or contributors, leading to inadequate maintenance.  
- There is a lack of standardized guidelines or coordination measures for achieving unified output formats and compatibility with commercial tools.

#### 4.x ...  

> **Note: The decision on whether to include Chapter 6 will be discussed after summarizing Chapter 5.**

> ### 5. Automation Strategy and Operational Process  
> This chapter discusses automated processes that contribute to improved SBOM quality and the integration of manual reviews where necessary.  
> 
> #### 5.1 Implementation of Automated Verification Tools  
> - Define policies for selecting and managing tools that can automatically check naming conventions, version formats, and required fields.  
> 
> #### 5.2 Conversion Processes and Normalization  
> - Outline the design and operational methods for transformation tools and data normalization processes to ensure consistency across different formats.  
> 
> #### 5.3 Reducing Operational Burdens and Integrating Manual Reviews  
> - Describe the integration of manual reviews as a hybrid operational flow following initial automated checks for handling exceptions and ambiguous information.

### 6. Guide Management and Administration  
This chapter focuses on managing the guide itself, outlining regular reviews, updates, and procedures for documenting change history rather than the operational management of the SBOMs.

#### 6.1 Guide Update Process  
- Establish a process for regular review and revision of the guide in response to advancements in industry standards, automated tools, and user feedback.  
- Clearly define the procedures for coordination and approval among stakeholders during updates.

#### 6.2 Change History Management and Documentation  
- Define methods and rules for documenting change history, including details such as changes made, update dates, and affected areas at each version.  
- Include measures to ensure the authenticity and transparency of the guide’s own documentation.

### 7. References and Related Materials  
- List reference sources including the [OpenChain Telco-SBOM-Guide](https://github.com/OpenChain-Project/Telco-WG) and international standards or related documents such as SPDX and NTIA SBOM Minimum Elements.

---

### Appendix-1. SBOM Sample

This section contains a sample SBOM file written in JSON format, which adheres to the specifications and includes exemplary values. It is intended for review by experts familiar with the SPDX and CycloneDX specifications.

### Appendix-2. Template for Chapter 5 Items

The template provided herein is used to add items to Chapter 5. Discussions (via GitHub Discussion or Issues) should be held regarding whether to include these items or make changes to the content.

#### 4.x [Challenge Title] (e.g., 4.1 Ensuring Accurate and Consistent Information Descriptions)

##### 4.x.1 Overview  
- Concisely describe the current state of the issue and the desired state.  
- Include a brief summary of the background and scope of the issue.  
- Diagrams or illustrations may be embedded to aid explanation.

##### 4.x.2 Improvement Measures  
- Provide specific measures to address the issue (e.g., implementing automated verification tools, unifying description rules, defining processes).  
- Detail the steps for executing the improvement measures.

##### 4.x.3 Evaluation Methods  
- Specify metrics to demonstrate the effectiveness of the improvement measures (e.g., what items will be checked by automated tools, how checklist completion rates are measured).  
- Outline methods for both quantitative and qualitative evaluations as well as the evaluation cycle.

##### 4.x.4 Risks and Considerations  
- Describe risks, contingency plans, and additional notes associated with implementing the improvement measures.
