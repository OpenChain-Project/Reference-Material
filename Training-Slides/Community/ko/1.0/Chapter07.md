# Chapter 7. Avoiding Compliance Pitfalls

## Compliance Pitfalls

This chapter will describe some potential pitfalls to avoid in the compliance process:

1. Intellectual Property (IP) pitfalls
2. License Compliance pitfalls
3. Compliance Process pitfalls

> Compliance 위험

> 이 장에서는 Compliance Process에서 피해야 할 몇 가지 잠재적인 위험에 대해 설명한다. 

> 1. 지적 재산 (IP) 관련 위험
2. License Compliance 관련 위험
3. Compliance Process 관련 위험

## Intellectual Property Pitfalls

- Type & Description
  - Unplanned inclusion of copyleft FOSS into proprietary or 3rd party code: 
    - This type of failure occurs during the development process when engineers add (or cut and paste) FOSS code into source code that is proprietary (to you to you or to a third party) in conflict with your FOSS policies.
- Discovery
  - This type of failure can be discovered by scanning or auditing the source code for possible matches with:
    - FOSS source code 
    - Copyright notices
  - Automated source code scanning tools may be used for this purpose
- Avoidance
  - This type of failure can be avoided by:
    - Offering training to engineering staff to bring awareness to compliance issues and to the different types and categories of FOSS licenses and the implications of including FOSS source code in proprietary source code
    - Conducting regular source code scans or audits for all the source code in the build environment (proprietary, 3rd party and FOSS)

> 지적 재산 관련 위험
- 유형 및 내용
  - Proprietary 혹은 3rd Party Code내에 의도치 않은 Copyleft FOSS의 포함: 
    - 이러한 유형의 오류는 개발 과정에서 개발자가 FOSS 정책과 맞지 않는 형태로 FOSS Code를 Proprietary Source Code에 추가(혹은 잘라서 붙여넣기)할 때 발생한다. 
- 발견 방법
  - 이러한 유형의 오류는 다음과 일치할 가능성이 있는지 Source Code의 Scanning 혹은 Auditing을 하여 발견할 수 있다. 
    - FOSS Source Code
    - 저작권 고지
  - 이 때, 자동화 Source Code Scanning Tool을 사용할 수도 있다. 
- 회피 방법
  - 이러한 유형의 오류는 다음과 같은 방법으로 피할 수 있다. 
    - 개발자들이 Compliance 이슈, 다양한 유형/종류의 FOSS License, Proprietary Source Code내에 FOSS Source Code를 포함시키는 것의 결과에 대해 인식할 수 있도록 교육을 제공한다. 
    - Build 환경의 모든 Source Code (Proprietary, 3rd Party, FOSS)에 대해 정기적인 Source Code Scan 및 Audit을 수행한다. 

## Intellectual Property Pitfalls

- Type & Description
  - Unplanned linking of copyleft FOSS into proprietary source code in certain cases  (or vice versa):  
    - This type of failure occurs as a result of linking software (FOSS, proprietary, 3rd party) that have conflicting or incompatible licenses. The legal effect of linking is subject to debate in the FOSS community.
- Discovery
  - This type of failure can be discovered using the dependency tracking tool that allows you to discover linkages between different software components.
- Avoidance
  - This type of failure can be avoided by:
    1. Offering training to engineering staff to avoid linking software components with licenses that conflict with you FOSS policies which will take a position on these legal risks
    2. Continuously running the dependency tracking tool over your build environment

> - 유형 및 내용
  - 의도치 않게 Copyleft FOSS를 Proprietary Source Code에 Linking하는 경우 (혹은 그 반대 경우): 
    - 이런 유형의 오류는 충돌 혹은 호환되지 않는 License의 Software(FOSS, Proprietary, 3rd Party)를 서로 Linking하는 결과로 발생한다. Linking에 대한 법률적 효과는 FOSS Community에서 논쟁의 대상이다. 
- 발견 방법
  - 이런 유형의 오류는 Dependency Tracking Tool(Software Component들 간의 연결관계를 보여주는 Tool)을 이용해 발견할 수 있다. 
- 회피 방법
  - 이런 유형의 오류는 다음과 같은 방법으로 피할 수 있다.: 
    1. 개발자들이 FOSS 정책과 맞지 않는 형태로 Software Component를 linking하는 것을 피할 수 있도록 교육을 제공한다. 
    2. Build 환경에서 Dependency Tracking Tool을 지속적으로 실행한다. 

- Type & Description
  - Inclusion of proprietary code into copyleft FOSS through source code modifications 
- Discovery
  - This type of failure can be discovered using the audits or scans to identify and analyze the source code you introduced to the FOSS component.
- Avoidance
  - This type of failures can be avoided by:
    1. Offering training to engineering staff
    2. Conducting regular code audits

> - 유형 및 내용
  - Source Code 수정을 통해 Proprietary Code를 Copyleft FOSS에 포함
- 발견 방법
  - 이런 유형의 오류는 Audit 혹은 Scan을 통해 FOSS Component에 추가한 Source Code를 식별 및 분석하여 발견할 수 있다. 
- 회피 방법
  - 이런 유형의 오류는 다음의 방법을 통해 피할 수 있다. 
    1. 개발자에게 교육 제공
    2. 주기적인 Code Audit 수행

## License Compliance Pitfalls

- Type & Description 
  - Failure to Provide Accompanying Source Code
- Avoidance
  - This type of failure can be avoided by making source code publishing a checklist item in the product release cycle before the product becomes available in the market place.
- Type & Description 
  - Providing the Incorrect Version of Accompanying Source Code
- Avoidance
  - This type of failure can be avoided by adding a verification step into the compliance process to ensure that the accompanying source code for the binary version is being published.
- Type & Description 
  - Failure to Publish Accompanying Source Code for FOSS Component Modifications 
- Avoidance
  - This type of failure can be avoided by adding a verification step into the compliance process to ensure that source code for modifications are published, rather than only the original source code for the FOSS component

> License Compliance 관련 위험
- 유형 및 내용
  - 동반하는 Source Code 제공 실패
- 회피 방법
  - 이런 유형의 오류는 Source Code 공개를 제품 출시를 위한 Checklist 항목으로 관리함으로 피할 수 있다. 
- 유형 및 내용
  - 잘못된 Version으로 동반하는 Source Code 제공
- 회피 방법
  - Binary version과 일치하는 Source Code 공개를 보장하기 위한 확인 단계를 Compliance Process에 추가함으로 이런 유형의 오류를 피할 수 있다. 
- 유형 및 내용
  - 수정한 FOSS Component에 대해 동반하는 Source Code 제공 실패
- 회피 방법
  - FOSS Component의 원본 Source Code 뿐만 아니라 수정한 Source Code에 대해서도 공개를 보장하기 위한 확인 단계를 Compliance Process에 추가함으로 이런 유형의 오류를 피할 수 있다. 

## License Compliance Pitfalls
- Type & Description 
  - Failure to mark FOSS Source Code Modifications: 
    - Failure to mark FOSS source code that has been changed or failure to include a description of the changes.
- Avoidance
  - This type of failure can be avoided by:
    1. Adding source code modification marking as a verification step before releasing the source code 
    2. Offering training to engineering staff to ensure they update copyright markings or license information of all FOSS or proprietary software that is going to be released to the public

> License Compliance 관련 위험
- 유형 및 내용
  - FOSS Source Code에 수정 내용 표시 실패
    - FOSS Source Code에 수정 내용을 표시하지 않거나 수정사항에 대한 설명을 포함하지 않음
- 회피 방법
  - 이런 유형의 오류는 다음의 방법을 통해 피할 수 있다. 
    1. Source Code 수정 내용 표시 과정을 Source Code 공개 전 확인 단계로 추가
    2. 개발자들에게 일반 대중에게 공개할 예정인 모든 FOSS 혹은 Proprietary Software에 대해 Copyright 표시 및 License 정보 update를 수행할 수 있도록 교육 제공

## Compliance Process Failures
- Description 
  - Failure by developers to seek approval to use FOSS
- Avoidance
  - This type of failure can be avoided by offering training to Engineering staff on the company’s FOSS policies and processes.
- Prevention
  - This type of failure can be prevented by:
    1. Conducting periodic full scan for the software platform to detect any “undeclared” FOSS usage
    2. Offering training to engineering staff on the company's FOSS policies and processes
    3. Including compliance in the employees performance review
- Description
  - Failure to take the FOSS training
- Avoidance
  - This type of failure can be avoided by ensuring that the completion of the FOSS training is part of the employee’s professional development plan and it is monitored for completion as part of the performance review 
- Prevention
  - This type of failure can be prevented by mandating engineering staff to take the FOSS training by a specific date 

> Compliance Process 관련 위험
- 내용
  - 개발자가 FOSS 사용 승인을 받지 않음
- 회피 방법
  - 이런 유형의 오류는 개발자에게 회사의 FOSS 정책 및 Process에 대해 교육을 제공함으로 피할 수 있다. 
- 예방 방법
  - 이런 유형의 오류는 다음 방법을 통해 예방할 수 있다. 
    1. Software Platform에 대해 정기적으로 Full Scan을 수행하여 확인되지 않은 FOSS의 사용을 발견한다. 
    2. 개발자에게 회사의 FOSS 정책 및 Process에 대해 교육을 제공한다. 
    3. 직원 성과 평가 시 Compliance 항목을 추가한다. 
- 내용
  - FOSS 교육을 수강하지 않음
- 회피 방법
  - FOSS 교육 수강을 직원의 전문 개발 계획의 일부임을 보장하고 직원 성과의 일부로 수강 여부를 감독함으로 이런 유형의 오류를 피할 수 있다. 
- 예방 방법
  - 이런 유형의 오류는 개발자들에게 특정 날짜까지 FOSS 교육을 수강하도록 요구함으로써 예방할 수 있다. 

## Compliance Process Failures
- Description
  - Failure to audit the source code
- Avoidance 
  - This type of failure can be avoided by:
    1. Conducting periodic source code scans/audits 
    2. Ensuring that auditing is a milestone in the iterative development process 
- Prevention
  - This type of failure can be prevented by:
    1. Providing proper staffing as to not fall behind in schedule
    2. Enforcing periodic audits 


- Description
  - Failure to resolve the audit findings (analyzing the "hits" reported by a scan tool or audit)
- Avoidance 
  - This type of failure can be avoided by not allowing a compliance ticket to be resolved (i.e. closed) if the audit report is not finalized. 
- Prevention
  - This type of failure can be prevented by implementing blocks in approvals in the FOSS compliance process

- Description
  - Failure to seek review of FOSS in a timely manner
- Avoidance 
  - This type of failure can be avoided by initiating FOSS Review requests early even if engineering did not yet decide on the adoption of the FOSS source code
- Prevention
  - This type of failure can be prevented through education

> Compliance Process 관련 실패
- 내용
  - Source Code Audit 미수행
- 회피 방법
  - 이런 유형의 오류는 다음의 방법으로 피할 수 있다. 
    1. 정기적인 Source Code Scan/Audit 수행
    2. Audit을 반복적인 개발 Process내 하나의 주요한 단계로 보장
- 예방 방법
  - 이런 유형의 오류는 다음의 방법으로 예방할 수 있다. 
    1. 예정보다 늦어지지 않도록 적절한 인원 제공
    2. 정기적인 Audit 실시
- 내용
  - Audit을 통해 발견한 결과(Scan Tool 혹은 Audit에 의해 보고된 "hits"의 분석에 의한 결과)를 해결하지 않음
- 회피 방법
  - Audit 보고서가 완료되지 않은 경우, 문제가 해결되었다는 Compliance 증명서를 발급하지 않음으로 이러한 유형의 오류를 피할 수 있다. 
- 예방 방법
  - 이런 유형의 오류는 FOSS Compliance Process에 승인 절차를 추가함으로 예방할 수 있다. 
- 내용
  - FOSS에 대한 검토를 적절한 시기에 진행하지 않음
- 회피 방법
  - 개발자가 FOSS Source Code의 채택을 아직 결정하지 않았더라도 조기에 FOSS Review 요청을 시작함으로써 이런 유형의 오류를 피할 수 있다. 
- 예방 방법
  - 이런 유형의 오류는 교육을 통해 예방할 수 있다. 

## Ensure Compliance Prior to Product Shipment
- Companies must make compliance a priority before any product (in whatever form) ships
- Prioritizing compliance promotes:
  - More effective use of FOSS within your organization
  - Better relations with the FOSS community and FOSS organizations

> 제품 출하 전 Compliance의 보장
- 기업은 (어떤 형태로든) 제품 출하 이전에 Compliance를 우선시하여야 한다. 
- Compliance를 우선시하면 다음 사항이 개선된다. 
  - 조직 내에서 보다 효과적으로 FOSS를 사용함
  - FOSS Community 및 FOSS 기관들과의 관계 개선

## Establishing Community Relationships
- As a company that uses FOSS in commercial product, it is best to create and maintain a good relationship with the FOSS community, in particular, the specific communities related to the FOSS projects you use and deploy in your commercial product. 
- In addition, good relationships with FOSS organizations can be very helpful in advising on best way to be compliant and also help out if you experience a compliance issue.
- Good relationships with the software communities may also be helpful for two-way communication: upstreaming improvements and getting support from the software developers.

> Community와의 관계 확립
- 상용 제품에 FOSS를 사용하는 기업이라면 FOSS Community (특히, 제품에 사용 및 배포하는 FOSS Project와 관계된 FOSS Community) 와 좋은 관계를 유지하는 것이 대단히 유리하다. 
- 게다가, FOSS 기관과의 좋은 관계는 Compliance를 위한 최선의 방안에 대해 도움을 받을 수 있고, Compliance 이슈가 발생할 경우에도 도움이 된다. 
- 또한, Software Community와의 좋은 관계는 양방향 Communication에 도움이 될 수 있다. : Upstreaming 개선 및 Software 개발자로부터의 지원을 받을 수 있다. 

## Check Your Understanding
- What types of pitfalls can occur in FOSS compliance? 
- Give an example of an intellectual property failure.
- Give an example of a license compliance failure.
- Give an example of an compliance process failure.
- What are the benefits of prioritizing compliance?
- What are the benefits of maintaining a good community relationship?

> Check Your Understanding
- FOSS Compliance 관련 어떤 유형의 위험이 있을 수 있나?
- 지적 재산 관련 실패 사례를 제시하시오. 
- License Compliance 관련 실패 사례를 제시하시오. 
- Compliance Process 관련 실패 사례를 제시하시오. 
- Compliance에 우선순위를 두었을 때의 장점은 무엇인가?
- Community와 좋은 관계를 유지하는 것의 장점은 무엇인가? 
