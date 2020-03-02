# Chapter 3. Introduction to FOSS Compliance

## FOSS Compliance Goals
- **Know your obligations (detect and track use of FOSS).** You should have a process for identifying, tracking and archiving a list of all FOSS components (and their respective identified licenses) from which your software is comprised.

- **Satisfy all the license obligations for the FOSS that is used.** Your program should identify and handle typical FOSS use cases that result from your organization’s business practices.

> FOSS Compliance 목표
- **의무 사항이 무엇인지 파악한다.(FOSS의 사용을 발견하고 추적하라.)** Software를 개발하면서 포함하는 모든 FOSS Component(및 각각 확인한 License)를 식별, 추적, 보관하는 Process가 있어야 한다. 
- **사용한 FOSS의 모든 License 의무 사항을 준수한다.** 귀사의 Program은 조직의 사업 형태에서 비롯되는 일반적인 FOSS의 Use Case를 식별하고 처리해야 한다. 

## What Compliance Obligations Must Be Satisfied?
Depending on the license(s) involved, obligations could consist of:
- **Attribution and Notices.** Inclusion of copyright and license text in the source code and/or product documentation or user interface, so that downstream users know the origin of the software and their rights under the licenses 
- **Source code availability.** Providing source code for original work, for combined work or modifications, as well as build scripts (scripts that control the build process)

These obligations may trigger upon key events, such as:
- External distribution 
- Whether you have made modifications

> 준수해야 할 Compliance 의무 사항은 무엇인가?
관련된 License에 따라 다음의 의무 사항이 있다: 
- **저작자 표시 및 고지.** 저작권 및 License Text를 Source Code 및/또는 제품 문서 혹은 User Interface에 포함하여 후속 사용자들이 Software의 출처와 License에 따른 권리를 알 수 있게 한다. 
- **Source Code 공개.** 원저작물, 결합저작물, 수정사항에 대해 Source Code뿐만 아니라 Build Script (Build Process를 제어하는 Script)를 제공한다. 

> 이러한 의무 사항은 다음과 같은 주요 Event에 따라 유발될 수 있다: 
- 외부 배포
- 수정 여부

## FOSS Conditions & Restrictions
Depending on the FOSS license used, you may need to comply with one or more of the following types of conditions and restrictions:
- Retain copyright (and other) notices
- Provide a copy of the license
- Provide notice of modifications
- Modified versions must have a different name to avoid confusion
- Provide access to source code (whether you modified it or not)
- Maintain modified versions (derivative works) under the same license
- Provide attribution
- Do not use the project or copyright holder name or trademark 
- Do not restrict others of the rights granted under the original license
- Termination clauses (if you breach, you lose license)

> FOSS 조건 및 제한 사항

> 사용하는 FOSS License에 따라 다음 조건 및 제한사항을 하나 이상 준수해야 할 수 있다. 
- 저작권 (및 기타) 고지 유지
- License 사본 제공
- 수정 내용 고지 제공
- 수정 version은 혼란을 방지하기 위해 다른 이름을 사용해야만 함
- (수정 여부와 관계없이) 소스 코드에 대한 접근 권한 제공
- 수정 version (파생 저작물)에 대해 같은 License 유지
- 저작자 표시 제공
- Project 또는 저작권자 이름이나 상표를 사용하지 말 것
- 원 License 하에 부여된 권리를 타인에게 제한하지 말 것
- 종료 조항 (위반할 경우, License를 잃음)

## FOSS Compliance Triggers: Distribution
- Dissemination of material to an outside entity 
  - Applications downloaded to a user’s machine or mobile device
  - Javascript, web client, or other code that is downloaded to the user’s machine 
- For some FOSS licenses, access via a computer network can be a “trigger event.” The trigger is"users interacting with it remotely through a computer network."
  - Some licenses define the trigger event to include permitting access to software running on a server (e.g., all versions of the Affero GPL if the software is modified)

> FOSS Compliance Trigger : 배포 (Distribution)
- 외부 주체로 자료 전파
  - User의 컴퓨터 혹은 모바일 장치에 다운로드 된 Application
  - User의 컴퓨터에 다운로드 된 Javascript, Web Client 또는 다른 코드
- 일부 FOSS License의 경우, 컴퓨터 Network을 통한 접근도 "Trigger Event"가 될 수 있다. Trigger는 “컴퓨터 Network을 통해 원격으로 상호작용하는 User”이다.. 
  - 일부 License는 Server에서 동작하는 Software에 대해서도 Access를 허용하도록 Trigger Event를 정의한다. (예: Software가 수정된 경우 Affero GPL의 모든 version)

## FOSS Compliance Triggers: Modification
- Changes to the existing program (e.g., additions, deletions of code in a file, combining components together)
- Modifications may constitute a derivative work, and FOSS authors may limit or place obligations on modifications
- Modifications may trigger FOSS obligations, such as:
  - Notice of modification
  - Providing accompanying source code

> FOSS Compliance Triggers: 수정
- 기존 Program의 변경 (예: File내 Code의 추가, 삭제, Component 결합)
- 수정하는 것으로 파생저작물이 만들어 질 수 있으며, FOSS 저작자는 수정하는 것에 대해 의무를 제한하거나 부과할 수 있다. 
- 수정은 다음과 같은 FOSS 의무 사항을 유발시킬 수 있다. 
  - 수정 내용 고지
  - 동반 Source Code 제공

## FOSS Compliance Program
Organizations who have been successful at FOSS compliance have created their own FOSS Compliance Programs (consisting of policies, processes, training and tools) to:

1. Facilitate effective usage of FOSS in commercial products
2. Respect FOSS developer rights and comply with license obligations
3. Contribute and participate in open communities

> FOSS Compliance Program

> FOSS Compliance에 성공한 조직은 자신만의 FOSS Compliance Program (Policy, Process, Training, Tool 등으로 구성)을 갖고 있다. 이를 통해, 

> 1. 상용 제품에 FOSS를 효과적으로 사용할 수 있게 한다. 
2. FOSS 개발자의 권리를 존중하고, License 의무 사항을 준수한다. 
3. Open Community에 참여하고 기여한다. 

## Implementing Compliance Practices
Prepare business processes and sufficient staff to handle:
- Identification of the origin and license of FOSS software
- Tracking FOSS software within the development process
- Performing FOSS review and identifying license obligations
- Fulfillment of license obligations when product ships 
- Oversight for FOSS Compliance Program, creation of policy, and compliance decisions
- Training

> Compliance를 위한 실천 사항

> 다음 사항들을 처리하기 위한 Business Process와 충분한 인력을 준비한다. 
- FOSS Software의 출처와 License 식별
- 개발 Process 내에서 FOSS Software 추적
- FOSS 검토 수행 및 License 의무 사항 확인
- 제품 배포 시 License 의무 사항 이행
- FOSS Compliance Program, 정책 수립 및 Compliance 의사 결정에 대한 감독
- 교육

## Compliance Benefits
Benefits of a robust FOSS Compliance program include:
- Increased understanding of the benefits of FOSS and how it impacts your organization
- Increased understanding of the costs and risks associated with using FOSS 
- Better relations with the FOSS community and FOSS organizations
- Increased knowledge of available FOSS solutions 

> Compliance의 이점

> 강력한 FOSS Compliance Program의 이점은 다음과 같다. 
- FOSS의 이점과 조직에 미치는 영향에 대한 이해 증진
- FOSS의 이용과 관련된 비용과 위험에 대한 이해 증진
- FOSS Community와 FOSS 기관들과의 관계 개선
- 사용 가능한 FOSS Solution들에 대한 지식 증가

## Check Your Understanding
- What does FOSS compliance mean?
- What are two main goals of a FOSS Compliance Program?
- List and describe important business practices of a FOSS Compliance Program.
- What are some benefits of a FOSS Compliance Program?

> Check Your Understanding
- FOSS Compliance는 무엇을 의미하는가?
- FOSS Compliance Program의 두 가지 주요 목표는 무엇인가?
- FOSS Compliance Program의 중요한 Business 실천 사항을 열거하고 설명하시오..
- FOSS Compliance Program의 이점은 무엇인가?


