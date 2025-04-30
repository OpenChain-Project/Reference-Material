# Understanding How To Adopt The OpenChain Project Standards

## Your Options and Choices 

## A Guide for Small, Medium and Large Companies

The OpenChain Project is not *just* about license compliance or security. It is building a more trusted supply chain by developing business process frameworks. These frameworks define the key requirements of quality license, security or other compliance programs.

The OpenChain Project has developed two ISO/IEC standards to support its mission and to assist the market, OpenChain ISO/IEC 5230 for open source license compliance and OpenChain ISO/IEC 18974 for open source security assurance. These standards focus on risk reduction and trust through standardization of processes and demonstrable controls. They provide a baseline for good compliance approaches.

It is important to remember that *how* you meet the baselines provided by the standards is flexible. The OpenChain Project operates with the concept of defining key process points but being flexible about how the process content is implemented. This allows OpenChain standards to be used by companies of all sizes and in all markets.

## I. OpenChain ISO/IEC 5230: Software Bill of Materials (SBOM) & License Compliance**

This standard concentrates on managing open source components, producing SBOMs, and ensuring license compliance.  Here's a breakdown of choices, by company size:

### A. Small Companies (1-50 Employees)

#### Resource Constraints

Limited budget, often no dedicated compliance or security staff, reliance on generalist developers.

#### Policy Communication

(a) Simple Email Communication: A brief email outlining the open source policy and pointing to a central document. *Pros:* Low cost, easy to implement. *Cons:* Low engagement, difficult to track.

(b) Brief Developer Onboarding Checklists: Integrate awareness of the policy into the standard onboarding process.  *Pros:*  Reaches all new developers. *Cons:* Requires more developer time.

#### SBOM Generation

(a) Manual Inventory:  A spreadsheet listing all open source components. *Pros:* Free, requires minimal tools. *Cons:* Time-consuming, error-prone, difficult to maintain.

(b) Basic Tooling (e.g., Black Duck Hub Community Edition):** Provides automated scanning, but with limited reporting. *Pros:* Reduces manual effort. *Cons:* Potential learning curve.

#### License Identification & Compliance

(a) Developer Responsibility: Developers are responsible for understanding and adhering to licenses. *Pros:* Low overhead. *Cons:* Relies heavily on individual knowledge, high risk of errors.

(b) Periodic Developer Review: Designated developer reviews open source usage regularly. *Pros:* Increases scrutiny. *Cons:* Still prone to errors, requires developer expertise.

#### Allowed Licenses

Start with a "whitelist" of permissive licenses (MIT, Apache 2.0, BSD) and require approval for others.  Consider the company's risk tolerance and use cases.

### B. Medium Companies (51-250 Employees)**

#### More Dedicated Staff: 

Possibly a dedicated security or compliance engineer.

#### Policy Communication

(a) Mandated Short Training Module (30-60 mins): Using platforms like Lessonly or internal Learning Management Systems. *Pros:* Higher engagement, demonstrates commitment. *Cons:* Requires platform and content creation.

(b) Integrate with Code Review Process: Policy reminders during code review. *Pros:* Directly links compliance to development. *Cons:* Requires training reviewers.

#### SBOM Generation

(a) Commercial Tooling (ScanCode, FOSSology, WhiteSource): More comprehensive reporting and automated updates. *Pros:* Automates much of the work. *Cons:* Ongoing costs.  ScanCode is excellent and has a free, self-managed option. FOSSology has a commercial service offering, in addition to the open source tools.

(b) Integrations with CI/CD Pipelines: Automatically generate SBOMs during builds. *Pros:* Real-time visibility. *Cons:* Requires pipeline modifications.

#### License Identification & Compliance

#### (a) Commercial Service Providers (e.g., Mend.io, Revenera):  Provide scanning, remediation advice, and ongoing monitoring. *Pros:* Expert assistance, reduced workload. *Cons:* Higher cost.

#### (b) Dedicated Compliance Engineer: Responsible for managing the process, scanning, and remediation. *Pros:* Focused expertise. *Cons:* Requires specialized skills and salary.

#### Allowed Licenses

Develop a more nuanced policy, allowing copyleft licenses (GPL, AGPL) under specific circumstances or with legal review.

### C. Large Companies (251+ Employees)

#### Dedicated Teams

Security, compliance, legal, and DevOps teams.

#### Policy Communication

(a) Formal, Company-Wide Training Program: Regularly updated and reinforced through ongoing communication. *Pros:* Strong commitment and understanding. *Cons:* Requires significant investment.

(b) Automated Enforcement in CI/CD: Prevent developers from including components with prohibited licenses. *Pros:* Prevents errors at the source. *Cons:*  Can be complex to implement.

#### SBOM Generation:**

(a) Full Suite Commercial Solutions:  Including continuous monitoring, vulnerability analysis, and automated remediation. *Pros:* Comprehensive protection. *Cons:*  Significant cost.

(b) Integrations with Internal Systems: Connect SBOM generation with procurement, contract management, and risk management tools. *Pros:* Holistic view of risk. *Cons:*  Requires system integrations.

#### License Identification & Compliance:

(a) Automated Policy Enforcement: Prevent development from adding components with restricted licenses. *Pros:* Eliminates manual errors. *Cons:* Requires policy configuration.

(b) Legal Review of High-Risk Components: Involve legal counsel for components with complex licenses or copyleft implications. *Pros:* Expert guidance. *Cons:* Can slow down development.

#### Allowed Licenses: Categorize licenses based on risk level and define approval workflows for each category.

## II. OpenChain ISO/IEC 18974: Software Security Assurance**

This standard focuses on identifying and managing vulnerabilities in open source components, and assuring the security of the software supply chain.

### A. Small to Large Companies (General Trends)

#### CVE Tracking

Regardless of size, start tracking CVEs (Common Vulnerabilities and Exposures) impacting your open source components.

#### Vulnerability Management Process

(a) Manual Review of Security Advisories: Review security advisories from vendors and security researchers. *Pros:* Free. *Cons:* Time-consuming, prone to errors.

(b) Commercial Vulnerability Database Subscriptions (e.g., Snyk, Sonatype): Provides automated vulnerability identification and remediation advice. *Pros:* Faster, more accurate. *Cons:* Ongoing costs.

#### Prioritization

Prioritize remediation based on the severity of the vulnerability, the component's criticality to your application, and the likelihood of exploitation.

#### Remediation Options

(a) Upgrading Components:  Updating to versions with patched vulnerabilities.
(b) Patching: Applying custom patches (not always feasible).
(c) Compensating Controls:  Implementing safeguards to mitigate the risk of exploitation.

#### Automation Tooling

Tools like Dependabot (GitHub), Renovate, and automated patching services can help streamline the remediation process.

### B. Choices Based on Company Size**

#### Small

Focus on critical vulnerabilities, using free or low-cost tooling.

#### Medium

Implement a more structured vulnerability management program with commercial tooling and dedicated resources.

#### Large

Integrate vulnerability management with broader security and risk management programs, automate patching, and regularly conduct security audits.

## Resources

1. OpenChain Project:** [https://openchainproject.org/](https://openchainproject.org/)
2. NIST National Vulnerability Database:** [https://nvd.nist.gov/](https://nvd.nist.gov/)

## Key Takeaway

OpenChain ISO/IEC 5230 and ISO/IEC 18974 offer a framework for improving open source license compliance and security security assurance. The specific implementation choices of using either standard should be tailored to your organization's size, resources, and risk tolerance.  Focus on establishing a simple, core management process, then automating as much as possible or iterating complexity over time, and remember to continuously monitor your software supply chain to catch external issues or address them in a timely manner.

# Original LLM Output Below - NOT FOR USE - REFERENCE ONLY

PROMPT for Gemma 3 12b IT-QAT on Ollama (gemma3:12b-it-qat)

Write an extremely detailed guide about the implementation choices that small, medium and large companies have when adopting BOTH OpenChain ISO/IEC 5230 for open source license compliance and OpenChain ISO/IEC 18974 for security assurance. Remember that the OpenChain Project covers more than license compliance or security assurance, and more generally is seeking to reduce risk in the supply chain, and increase trust in the supply chain. Take into account the different resources small, medium and large companies are likely to have access to, and explicitly reference the different type of options they are likely to have when addressing each challenge when implementing the ISO/IEC standards. Make sure to provide plenty of examples. On the license compliance side, focus on choices like how to inform staff of the existence of an open source policy, with an example being to (a) inform them by email or (b) inform them by a mandatory training. Make sure that the element of choice is included in each option presented, and no implementation options are presented as mandatory. Emphasize that the choice between simple or complex *process content* matters less than the *existence of the process* itself. Give plenty of examples related to how people may choose to implement OpenChain ISO/IEC 5230 requirements. For example, the choice between SBOM formats, or the choice between managing software compliance manually or with automated tooling. Give practical examples of open source compliance tooling options like ScanCode and FOSSology. Make reference to commercial service providers. Explain the topics when deciding what open source licenses to allow. Give plenty of examples related to how people may choose to implement OpenChain ISO/IEC 18974 requirements. Make sure to reference CVEs, knowledge vulnerability management best practices, and automation tooling available to support this area. Describe the availability of support through the OpenChain Project website, its online GitHub reference library of reference material, and the work groups that meet globally and locally to share knowledge.

== Output from Gemma Below ==

Okay, here's a detailed guide addressing implementation choices for OpenChain ISO/IEC 5230 (license compliance) and ISO/IEC 18974 (security assurance), tailored for small, medium, and large companies.  It's structured to highlight the *choices* available, rather than prescriptive steps. I'll emphasize the importance of *having* a process over its complexity.  I'll also incorporate practical tooling and service provider references.

**Understanding OpenChain's Broad Scope**

Before diving in, remember that OpenChain isn't *just* about license compliance or security. It's a framework for building a trustworthy and resilient software supply chain.  It focuses on risk reduction and trust building through standardization of processes and demonstrable controls.  The ISO/IEC standards provide a baseline, but *how* you meet those baselines is flexible.

**I. OpenChain ISO/IEC 5230: Software Bill of Materials (SBOM) & License Compliance**

This standard concentrates on managing open source components, producing SBOMs, and ensuring license compliance.  Here's a breakdown of choices, by company size:

**A. Small Companies (1-50 Employees)**

* **Resource Constraints:** Limited budget, often no dedicated compliance or security staff, reliance on generalist developers.
* **Policy Communication:**
  * **(a) Simple Email Communication:** A brief email outlining the open source policy and pointing to a central document. *Pros:* Low cost, easy to implement. *Cons:* Low engagement, difficult to track.
  * **(b) Brief Developer Onboarding Checklists:** Integrate awareness of the policy into the standard onboarding process.  *Pros:*  Reaches all new developers. *Cons:* Requires more developer time.
* **SBOM Generation:**
  * **(a) Manual Inventory:**  A spreadsheet listing all open source components. *Pros:* Free, requires minimal tools. *Cons:* Time-consuming, error-prone, difficult to maintain.
  * **(b) Basic Tooling (e.g., Black Duck Hub Community Edition):** Provides automated scanning, but with limited reporting. *Pros:* Reduces manual effort. *Cons:* Potential learning curve.
* **License Identification & Compliance:**
  * **(a) Developer Responsibility:** Developers are responsible for understanding and adhering to licenses. *Pros:* Low overhead. *Cons:* Relies heavily on individual knowledge, high risk of errors.
  * **(b) Periodic Developer Review:** Designated developer reviews open source usage regularly. *Pros:* Increases scrutiny. *Cons:* Still prone to errors, requires developer expertise.
* **Allowed Licenses:** Start with a "whitelist" of permissive licenses (MIT, Apache 2.0, BSD) and require approval for others.  Consider the company's risk tolerance and use cases.

**B. Medium Companies (51-250 Employees)**

* **More Dedicated Staff:** Possibly a dedicated security or compliance engineer.
* **Policy Communication:**
  * **(a) Mandated Short Training Module (30-60 mins):** Using platforms like Lessonly or internal Learning Management Systems. *Pros:* Higher engagement, demonstrates commitment. *Cons:* Requires platform and content creation.
  * **(b) Integrate with Code Review Process:** Policy reminders during code review. *Pros:* Directly links compliance to development. *Cons:* Requires training reviewers.
* **SBOM Generation:**
  * **(a) Commercial Tooling (ScanCode, FOSSology, WhiteSource):** More comprehensive reporting and automated updates. *Pros:* Automates much of the work. *Cons:* Ongoing costs.  ScanCode is excellent and has a free, self-managed option. FOSSology has a commercial service offering, in addition to the open source tools.
  * **(b) Integrations with CI/CD Pipelines:** Automatically generate SBOMs during builds. *Pros:* Real-time visibility. *Cons:* Requires pipeline modifications.
* **License Identification & Compliance:**
  * **(a) Commercial Service Providers (e.g., Mend.io, Revenera):**  Provide scanning, remediation advice, and ongoing monitoring. *Pros:* Expert assistance, reduced workload. *Cons:* Higher cost.
  * **(b) Dedicated Compliance Engineer:** Responsible for managing the process, scanning, and remediation. *Pros:* Focused expertise. *Cons:* Requires specialized skills and salary.
* **Allowed Licenses:** Develop a more nuanced policy, allowing copyleft licenses (GPL, AGPL) under specific circumstances or with legal review.

**C. Large Companies (251+ Employees)**

* **Dedicated Teams:** Security, compliance, legal, and DevOps teams.
* **Policy Communication:**
  * **(a) Formal, Company-Wide Training Program:** Regularly updated and reinforced through ongoing communication. *Pros:* Strong commitment and understanding. *Cons:* Requires significant investment.
  * **(b) Automated Enforcement in CI/CD:**  Prevent developers from including components with prohibited licenses. *Pros:* Prevents errors at the source. *Cons:*  Can be complex to implement.
* **SBOM Generation:**
  * **(a) Full Suite Commercial Solutions:**  Including continuous monitoring, vulnerability analysis, and automated remediation. *Pros:* Comprehensive protection. *Cons:*  Significant cost.
  * **(b) Integrations with Internal Systems:** Connect SBOM generation with procurement, contract management, and risk management tools. *Pros:* Holistic view of risk. *Cons:*  Requires system integrations.
* **License Identification & Compliance:**
  * **(a) Automated Policy Enforcement:** Prevent development from adding components with restricted licenses. *Pros:* Eliminates manual errors. *Cons:* Requires policy configuration.
  * **(b) Legal Review of High-Risk Components:**  Involve legal counsel for components with complex licenses or copyleft implications. *Pros:* Expert guidance. *Cons:* Can slow down development.
* **Allowed Licenses:** Categorize licenses based on risk level and define approval workflows for each category.

**II. OpenChain ISO/IEC 18974: Software Security Assurance**

This standard focuses on identifying and managing vulnerabilities in open source components, and assuring the security of the software supply chain.

**A. Small to Large Companies (General Trends)**

* **CVE Tracking:** Regardless of size, start tracking CVEs (Common Vulnerabilities and Exposures) impacting your open source components.
* **Vulnerability Management Process:**
  * **(a) Manual Review of Security Advisories:** Review security advisories from vendors and security researchers. *Pros:* Free. *Cons:* Time-consuming, prone to errors.
  * **(b) Commercial Vulnerability Database Subscriptions (e.g., Snyk, Sonatype):** Provides automated vulnerability identification and remediation advice. *Pros:* Faster, more accurate. *Cons:* Ongoing costs.
* **Prioritization:** Prioritize remediation based on the severity of the vulnerability, the component's criticality to your application, and the likelihood of exploitation.
* **Remediation Options:**
  * **(a) Upgrading Components:**  Updating to versions with patched vulnerabilities.
  * **(b) Patching:** Applying custom patches (not always feasible).
  * **(c) Compensating Controls:**  Implementing safeguards to mitigate the risk of exploitation.
* **Automation Tooling:** Tools like Dependabot (GitHub), Renovate, and automated patching services can help streamline the remediation process.

**B. Choices Based on Company Size**

* **Small:** Focus on critical vulnerabilities, using free or low-cost tooling.
* **Medium:** Implement a more structured vulnerability management program with commercial tooling and dedicated resources.
* **Large:** Integrate vulnerability management with broader security and risk management programs, automate patching, and regularly conduct security audits.

**Resources**

* **OpenChain:** [https://openchainproject.org/](https://openchainproject.org/)
* **NIST National Vulnerability Database:** [https://nvd.nist.gov/](https://nvd.nist.gov/)
* **Snyk:** [https://snyk.io/](https://snyk.io/)
* **Sonatype:** [https://www.sonatype.com/](https://www.sonatype.com/)

**Key Takeaway:**  OpenChain and ISO 18974 offer a framework for improving software security, but the specific implementation should be tailored to your organization's size, resources, and risk tolerance.  Focus on establishing a robust vulnerability management process, automating as much as possible, and continuously monitoring your software supply chain.
