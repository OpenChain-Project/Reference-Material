# Chapter 6. End to End Compliance Management (Example Process)

## Introduction
- Compliance management consists of a set of actions that controls the intake and distribution of FOSS used in products (or "Supplied Software" in the OpenChain specification) 
- The result of compliance due diligence is an identification of all FOSS used in the Supplied Software and confirmation that all FOSS license obligations have been or will be met
- This chapter provides an example of such a process, and may serve as a resource for forming or improving your internal processes  
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/introduction.png)

> 소개
- Compliance Management는 제품 (혹은 OpenChain Specification 에서의 "Supplied Software") 에 사용된 FOSS의 유입 및 배포를 제어하는 일련의 활동으로 구성된다. 
- Compliance를 위한 기업 실사(due diligence)의 결과는 Supplied Software내 사용된 모든 FOSS를 식별하고, 모든 FOSS License 의무 사항이 충족된다고 보장하는 것이다. 
- 이 장에서는 이러한 Process의 예를 제공하여 내부 Process를 구축하거나 개선하기 위한 도움을 제공한다. 

## Process Overview
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/processoverview.png)

- Identify FOSS components for review
- Scan or audit source code and 
  - Confirm origin and license of source code
- Resolve any audit issues in line with company FOSS policies
- Review and approve compliance record of FOSS software components
- Record approved software/version in inventory per product and per release
- Compile notices for publication
- Verify source code packages for distribution and 
  - Verify appropriate notices are provided
- Post publication verifications
- Publish source code, notices and provide written offer

Example of Compliance Management End-to-End Process

> Process Overview
- Review를 위한 FOSS Component 식별
- Source Code Scan 및 Audit
  - Source Code 출처 및 License 확인
- 회사 FOSS 정책에 맞게 Audit 이슈 해결
- FOSS Software Component의 Compliance 기록 검토 및 승인
- 제품별, Release별 목록표 (inventory) 내 승인된 Software/Version 기록
- 공개를 위한 고지문 편집
- 배포를 위한 Source Code Package 확인
  - 적절한 고지문이 제공되는지 확인
- 확인된 산출물 게시
- Source Code, 고지문 공개 및 약정서 제공

> Compliance Management End-to-End Process 의 예

# Identify and Track FOSS Usage

![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/track.png)

Identify and begin tracking FOSS from all sources

- Pre-requisites:
The process may begin with one of these events:
  - The development team requests the review of a FOSS component or an outgoing release
  - Discovery of FOSS being used without proper authorization
  - Discovery of FOSS being used as part of third party software 
- Steps: 
  - Incoming requests are recorded
  - Scans of entire platform may be performed
  - Due diligence on any 3rd party provided software
  - Recognize and review any FOSS components added to a repository without an incoming request
- Outcome: 
  - A compliance record is created (or updated) for the FOSS 
  - An audit is requested to scan or review the source code


> FOSS 사용의 확인 및 추적

> 모든 Sourced에 대해 FOSS를 확인하고 추적한다
- 전제 조건 : Process는 다음 중 하나의 이벤트로 시작할 수 있다. 
  - 개발팀에서 FOSS Component의 검토 혹은 외부 배포 요청
  - 적절한 승인 없이 사용된 FOSS의 발견
  - 3rd Party Software의 일부로 사용된 FOSS의 발견
- 단계 : 
  - 접수된 요청 기록
  - 전체 Platform에 대한 Scan을 수행할 수 있음
  - 3rd Party 제공 Software에 대한 실사 (Due Diligence)
  - 접수된 요청 없이 repository에 추가된 모든 FOSS Component에 대해 인식 및 검토
- 결과 : 
  - FOSS에 대한 Compliance 기록 생성 (혹은 갱신)
  - Source Code를 Scan하거나 Review하도록 Audit 요청

## Auditing Source Code
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/auditing.png)

Identify FOSS components and their origin and licenses 

- Pre-requisites:
  - Development team provides a compliance record with information about the FOSS usage 
  - In cases where no record is provided by the development team, a record can be created when the FOSS component is discovered
- Steps: 
  - Source code for the audit is identified
  - Source may be scanned by a software tool
  - “Hits” from the audit or scan are reviewed and verified as to the proper origin of the code
  - Audits or scans are performed iteratively based on the software development and release lifecycles
- Outcome: 
  - An audit report identifying the origins and licenses of the source code 

> Source Code Auditing

> FOSS Component를 식별하여 출처 및 License를 확인한다. 
- 전제 조건: 
  - 개발팀은 FOSS 사용에 대한 정보가 담긴 Compliance 기록을 제공한다. 
  - 개발팀에서 제공한 기록이 없을 경우, 발견되는 FOSS Component로 기록을 만들 수 있다. 
- 단계:
  - Audit을 위한 Source Code 식별
  - Source Code Scan을 위해 Software Tool의 사용이 가능하다.
  - Audit 혹은 Scan을 통해 발견된 부분은 Code의 적절한 출처에 대해 검토 및 확인되어야 한다.
  - Audit 혹은 Scan은 Software 개발 및 Release Lifecycle에 따라 반복적으로 수행되어야 한다.
- 결과:
  - Source Code의 출처와 License를 식별한 Audit Report

## Resolving Issues
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/resolving.png)

Resolve all issues identified in the audit

- Pre-requisites:
  - A source code audit or scan has been completed 
  - An audit report identifies the origins and licenses of the source code and flags files that need further investigation
- Steps: 
  - Provide feedback to the appropriate engineers to resolve issues in the audit report that conflict with your FOSS policy 
  - Follow up with engineers to confirm that the issues are resolved
- Outcome: 
  - A resolution for each of the flagged files in the report and a resolution for any flagged license conflict 

> Resolving Issues

> Audit을 통해 확인한 모든 이슈들을 해결한다. 
- 전제조건:
  - Source Code Audit 혹은 Scan을 완료하였다. 
  - Audit Report는 Source Code의 출처 및 License를 식별하고, 추가 조사가 필요한 file에 대해 표시하였다. 
- 단계:
  - FOSS 정책과 충돌하는 Audit Report내의 이슈 해결을 위해 적합한 Engineer에게 피드백을 제공한다. 
  - Engineer와 상의하여 문제가 해결되었는지를 확인한다. 
- 결과 : 
  - Report내 각 체크된 파일의 해결 및 충돌되는 License의 해결

## Performing Reviews
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/performing.png)

Review the audit report and confirm any discovered issues are resolved

- Pre-requisites:
  - Source code has been audited 
  - All identified issues have been resolved

- Steps: 
  - Include appropriate authority levels in review staff
  - Conduct FOSS Reviews on audited source code, review software architecture and FOSS usage (see next slide for template)
  - Identify obligations under FOSS licenses

- Outcome: 
  - Ensure the software in the audit report conforms with FOSS policies 
  - Preserve audit report findings and mark resolved issues as ready for the next step (i.e. Approval)


> Review 수행

> Audit Report를 검토하고 발견된 이슈들이 해결되었는지를 확인한다. 
- 전제조건:
  - Source Code가 Audit되었다. 
  - 모든 확인된 이슈들은 해결되었다. 
- 단계:
  - 검토하는 직원에게 적절한 수준의 권한 을 제공한다. 
  - Audit된 Source Code에 대해 FOSS Review를 수행하고, Software Architecture 및 FOSS 사용을 검토한다. (다음 Slide의 template참고)
  - FOSS License들의 의무 사항을 확인한다. 
- 결과: 
  - Audit Report의 Software가 FOSS 정책에 순응하는지 확인한다. 
  - Audit Report 결과를 보존하고, 다음 단계 (Approval) 를 위해 해결된 이슈들을 표시해둔다. 

## Architecture Review (Example Template)
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/exampletemplate.png)

## Approvals
- Based on the results of the software audit and review in previous steps, software may or may not be approved for use
- The approval should specify versions of approved FOSS components, the approved usage model for the component, and any other applicable obligations under the FOSS license
- Approvals should be made at appropriate authority levels
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/approval.png)

> Approval
- 이전 단계에서의 Software Audit 및 Review 결과에 따라 Software 사용이 승인될 수도, 되지 않을 수도 있다. 
- 승인된 FOSS Component의 Version, 승인된 Component의 사용 모델 및 FOSS License에 따른 의무사항들이 명시되어야 한다. 
- 승인은 적절한 수준의 권한에서 이루어져야 한다. 

## Registration / Approval Tracking
- Once a FOSS component has been approved for usage in a product, it should be added to the software inventory for that product 
- The approval and its conditions should be registered in a tracking system  
- The tracking system should make it clear that a new approval is needed for a new version of a FOSS component or if a new usage model is proposed  

![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/registration.png)

> Registration / Approval Tracking
- FOSS Component가 제품에서의 사용이 승인되면, 해당 제품의 Software 목록표에 추가되어야 한다. 
- 승인 및 이에 대한 조건은 Tracking System에 등록되어야 한다. 
- Tracking System은 FOSS Component의 신규 version 혹은 새로운 사용 모델이 제안된 경우 새로 승인이 될 수 있도록 해야 한다. 

## Notices
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/notices.png)

- Prepare appropriate notices for any FOSS used in a product release:
  - Acknowledge the use of FOSS by providing full copyright and attribution notices 
  - Inform the end user of their product on how to obtain a copy of the FOSS source code (when applicable, for example in the case of GPL and LGPL)
  - Reproduce the entire text of the license agreements for the FOSS code included in the product as needed 

> Notice
- Release하는 제품에 사용된 모든 FOSS에 대해 적절한 고지를 준비한다. 
  - 모든 저작권 및 저작자 고지를 제공하기 위해 FOSS의 사용을 표시한다. 
  - 제품의 최종 사용자에게 FOSS Source Code 사본을 어떻게 얻을 수 있는지 알린다 (GPL, LGPL과 같이 Source 공개가 필요한 경우). 
  - 필요에 따라 제품에 포함된 FOSS Code에 대한 License Agreement의 전체 text를 제공한다. 

## Pre-Distribution Verifications
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/predistributions.png)

Verify that distributed software has been reviewed and approved 

- Pre-requisites:
  - FOSS component has been approved for usage
  - FOSS component has been registered in the software inventory for the release
  - Appropriate notices have been prepared 
- Steps: 
  - Verify FOSS packages destined for distribution have been identified and approved
  - Verify the reviewed source code matches the binary equivalents shipping in the product
  - Verify all appropriate notices have been included to inform end-users of their right to request source code for identified FOSS
  - Verify compliance with other identified obligations 
- Outcome: 
  - The distribution package contains only software that has been reviewed and approved
  - "Distributed Compliance Artifacts" (as defined in the OpenChain specification), including appropriate notice files are included in the distribution package or other delivery method

> Pre-Distribution Verifications

> 배포된 Software가 Review 및 승인되었는지 확인한다. 
- 전제조건:
  - FOSS Component가 사용 승인 되었음
  - FOSS Component가 Release되는 Software의 목록표에 등록되었음
  - 적절한 고지문이 준비되었음
- 단계: 
  - 배포할 FOSS Package들이 식별되고 승인되었는지 확인한다. 
  - 검토된 Source Code가 제품 내의 Binary와 일치하는지 확인한다. 
  - 식별된 FOSS에 대해 Source Code 요청 권리가 있음을 최종 소비자에게 알리기 위한 적절한 고지문이 포함되었는지 확인한다. 
- 결과: 
  - 배포 Package에는 검토 승인된 Software만 포함한다.
  - 적절한 고지 File을 포함한 "배포 준수 산출물 (Distributed Compliance Artifacts : OpenChain 스펙에 정의)"을 배포 Package 혹은 다른 형태로 전달될 수 있도록 포함한다. 

## Accompanying Source Code Distribution

![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/distribution.png)

Provide accompanying source code as required 

- Pre-requisites:
  - All pre-distribution verification has been completed and no issue is discovered
- Steps: 
  - Provide accompanying source code along with any associated build tools and documentation (e.g., by uploading to a distribution website or including in the distribution package) 
  - Accompanying source code is identified with labels as to which product and version to which it corresponds
- Outcome: 
  - Obligations to provide accompanying source code are met

> 동반하는 Source Code Distribution

> 요구에 따라 동반하는 Source Code 제공
- 전제조건:
  - 배포 전 모든 사항이 확인 완료되었으며, 이슈는 발견되지 않음
- 단계:
  - 동반하는 Source Code를 관련 Build Tool 및 문서와 함께 제공한다 (예: 배포 사이트에 upload하거나 배포 Package내에 포함시키는 방법으로 제공)
  - 동반하는 Source Code는 제품 및 Version을 라벨(label)로 표시하여 식별되게 한다. 
- 결과:
  - 동반하는 Source Code를 제공하기 위한 의무 사항을 충족한다. 


## Final Verifications

![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/verification.png)

Validate compliance with license obligations

- Pre-requisites:
  - Accompanying source code is provided as may be required
  - Appropriate notices have been prepared 
- Steps: 
  - Verify accompanying source code (if any) has been uploaded or distributed correctly  
  - Verify uploaded or distributed source code corresponds to the same version that was approved 
  - Verify notices have been properly published and made available
  - Verify other identified obligations are met
- Outcome: 
  - Verified Distributed Compliance Artifacts are appropriately provided

>  Final Verifications

> License 의무사항 준수 여부를 인증한다. 
- 전제조건:
  - 동반하는 Source Code를 필요에 따라 제공한다. 
  - 적절한 고지문을 준비 하였다. 
- 단계:
  - 동반하는 Source Code가 (필요한 경우) 올바르게 upload되거나 배포되었는지 확인한다. 
  - Upload 혹은 배포된 Source Code가 승인된 version과 동일한지 확인한다. 
  - 고지문이 적절하게 게시 되었는지와 접근 가능한지 확인한다. 
  - 이외 다른 의무 사항들이 준수되었는지 확인한다. 
- 결과: 
  - 배포되는 Compliance 산출물들이 적절히 제공되었는지 확인한다. 

## Check Your Understanding
- What is involved in compliance due diligence (describe the steps at a high level)?
- What types of issues may need to be resolved as part of compliance management?
- Who should be involved in reviewing audit results?
- What does an architecture review look for?
- What should be included in the FOSS Notices?
- What needs to be distributed for code used under a copyleft license?

> Check Your Understanding
- Compliance를 위한 기업 실사(Due Diligence)를 위해 필요한 것은 무엇인가? (high level에서의 단계를 설명하라)
- Compliance Management의 일부로 해결해야 할 이슈 유형은 무엇인가?
- Audit 결과 검토에 누가 참여해야 하는가? 
- Architecture 검토는 무엇을 확인하기 위해서인가?
- FOSS 고지문에는 무엇이 포함되어야 하는가?
- Copyleft License하의 Code는 무엇이 배포되어야 하는가? 
