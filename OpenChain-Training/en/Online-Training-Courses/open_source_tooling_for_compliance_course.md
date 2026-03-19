# Training Course Outline  
## Open Source Tools & Solutions for Open Source License Compliance

---

## Course Overview
- **Audience**
  - Software engineers and architects responsible for build and release
  - Legal and compliance professionals supporting product delivery
  - OSPO members defining governance and tooling
  - DevSecOps teams integrating compliance into pipelines
- **Level**
  - Intermediate (assumes basic OSS awareness)
  - Advanced extensions for scale, automation, and audits
- **Format**
  - Modular delivery (can be split across multiple sessions)
  - Combination of lecture, discussion, and hands-on exercises
- **Learning Outcomes**
  - Translate legal license obligations into technical requirements
  - Design and operate automated compliance workflows
  - Evaluate and apply open source compliance tooling
  - Generate and review compliance deliverables
  - Embed compliance into modern software delivery processes

---

## Chapter 1: Open Source Compliance Concepts

### 1.1 What Is Open Source Compliance?
- Definition and scope of compliance activities
- Difference between:
  - License compliance
  - Security vulnerability management
  - Open source governance
- Risk categories
  - Legal exposure
  - Product shipment delays
  - Reputational and customer trust risks
- Typical compliance stakeholders and responsibilities

### 1.2 Key Compliance Artifacts
- Software Bill of Materials (SBOM)
  - Purpose and required content
- License inventory
  - Mapping components to licenses
- Notices and attributions
  - Aggregation and formatting requirements
- Source code offers
  - When they are required
  - Duration and delivery mechanisms
- Audit and evidence artifacts
  - Logs, reports, and approval records

### 1.3 Standards and Best Practices
- SPDX
  - License identifiers and expressions
  - Document structure and fields
- CycloneDX
  - Focus on supply chain transparency
- OpenChain ISO/IEC 5230
  - Organizational conformance requirements
- OpenSSF guidance
  - Integration of compliance with security practices

---

## Chapter 2: Open Source License Scanning & Discovery Tools

### 2.1 Source Code Scanning
- What scanners analyze
  - File headers
  - Embedded license texts
  - Copyright statements
- Detection methodologies
  - Exact matching
  - Heuristic and fuzzy matching
- Accuracy considerations
  - False positives
  - False negatives
- Limitations
  - Generated code
  - Minified or binary artifacts

### 2.2 Tool Categories
- Source code scanners  
- Package and dependency analyzers  
- Metadata and curation services  
- License identification libraries  

### 2.3 Hands-On Lab
- Selecting a representative project  
- Running an initial scan  
- Reviewing detected licenses and confidence levels  
- Identifying:
  - Unknown licenses  
  - Multiple licenses per component  
- Documenting findings for downstream review  

---

## Chapter 3: Dependency & Package Analysis

### 3.1 Dependency Management Basics
- How dependencies are introduced  
  - Direct dependencies  
  - Transitive dependencies  
- Dependency resolution  
  - Version constraints  
  - Lockfiles  
- Risks introduced by transitive dependencies  
- Language- and ecosystem-specific considerations  

### 3.2 Dependency Analysis Approaches
- Manifest-based analysis  
  - Declared dependencies only  
- Lockfile analysis  
  - Resolved dependency trees  
- Build-system introspection  
  - Actual artifacts used in builds  
- Pros and cons of each approach  

### 3.3 License Expression Handling
- SPDX license identifiers  
- Compound expressions  
  - AND / OR semantics  
- License exceptions  
- Dual-licensed components  
- Practical compatibility analysis scenarios  

---

## Chapter 4: Software Bill of Materials (SBOM)

### 4.1 Why SBOMs Matter
- Regulatory and policy drivers  
- Customer and partner requirements  
- Internal benefits  
  - Inventory visibility  
  - Faster compliance reviews  
- SBOMs as living documents vs point-in-time artifacts  

### 4.2 SBOM Formats and Tradeoffs
- SPDX  
  - Compliance and legal focus  
- CycloneDX  
  - Supply chain and security focus  
- Serialization formats  
  - Human-readable vs machine-readable  
- Interoperability considerations  

### 4.3 SBOM Generation Approaches
- Source-based generation  
- Binary-based generation  
- Container image analysis  
- Build-time generation  
  - Advantages for accuracy  
- Post-build generation  
  - Advantages for coverage  

### 4.4 Hands-On Lab
- Generate an SBOM for a sample artifact  
- Review required vs optional fields  
- Identify missing or ambiguous data  
- Connect SBOM entries to license obligations  

---

## Chapter 5: Policy, Governance & Automation

### 5.1 Defining Open Source Policies
- Purpose and scope of policies  
- License categorization  
  - Allowed  
  - Restricted  
  - Prohibited  
- Contribution and inbound licensing policies  
- Exception and escalation processes  

### 5.2 Automated Policy Enforcement
- Translating policy into rules  
- Policy-as-code concepts  
- Evaluation timing  
  - Pre-commit  
  - CI  
  - Release gates  
- Reporting and approval workflows  

### 5.3 CI/CD Integration
- Where compliance fits in pipelines  
- Incremental vs full scans  
- Handling policy violations  
  - Fail, warn, or escalate  
- Developer feedback and usability considerations  

---

## Chapter 6: Handling Compliance Issues

### 6.1 Common Compliance Problems
- Missing or incomplete license information  
- Conflicting licenses in dependency trees  
- Copyleft obligations misunderstood or misapplied  
- Custom or non-standard licenses  

### 6.2 Remediation Strategies
- Technical remediation  
  - Replacing or removing components  
- Legal remediation  
  - Clarifying intent and obligations  
- Documentation remediation  
  - Correcting notices and offers  
- Business decision tradeoffs  

### 6.3 Working with Legal & Engineering
- Defining clear handoffs  
- Shared vocabulary and documentation  
- Preparing for audits and due diligence  
- Continuous improvement feedback loops  

---

## Chapter 7: Open Source Compliance at Scale

### 7.1 Open Source Program Offices (OSPOs)
- Centralized vs federated models  
- Responsibilities  
  - Policy  
  - Tooling  
  - Education  
- Metrics  
  - Scan coverage  
  - Time to resolution  
- Continuous maturity improvement  

### 7.2 Compliance for Products & Distributions
- Product-specific challenges  
- Embedded and firmware constraints  
- Containers and cloud-native delivery  
- Long-term support and update obligations  

### 7.3 Case Studies
- Typical failure patterns  
- Root cause analysis  
- Preventative controls  
- Lessons learned for scaling organizations  

---

## Chapter 8: Emerging Trends & Future Directions
- Increasing regulation and standardization  
- SBOMs as compliance and security primitives  
- AI-generated code and license provenance  
- Model weights, datasets, and open source obligations  
- Convergence of compliance, security, and supply-chain risk  

---

## Capstone Exercise (Optional)
- Define compliance requirements for a sample product  
- Execute an end-to-end workflow  
- Produce:
  - Scan results  
  - SBOM  
  - Notices  
  - Policy evaluation report  
- Group review and discussion  

---

## Course Materials & Resources
- Standards and specification references  
- Sample compliance policies  
- Example artifacts and templates  
- Checklists for audits and releases  

---

# Appendix A: Example Open Source Tools and Implementations

### A.1 License Detection & Source Scanning
- ScanCode Toolkit  
- FOSSology  
- Licensee (GitHub)  

### A.2 Dependency & Package Analysis
- OSS Review Toolkit (ORT)  
- Syft  
- Eclipse Steady  
- REUSE Tool  

### A.3 SBOM Generation
- Syft  
- ORT  
- ScanCode  
- CycloneDX CLI  

### A.4 Policy Evaluation & Automation
- ORT Evaluator  
- Custom policy-as-code frameworks  

### A.5 Metadata & Curation
- ClearlyDefined  
