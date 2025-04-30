# Chapter 4. Key Software Concepts for FOSS Review

## What information do you need to gather?
When analyzing FOSS usage, collect information about the identity of the FOSS component, its origin, and how the FOSS component will be used. This may include:

- Package name
- Version
- Original download URL
- License and License URL
- Description
- Description of modifications
- List of dependencies
- Intended use in your product
- First product release that will include the package
- Availability of source code
- Where the source code will be maintained
- Whether the package had previously been approved for use in another context
- Inclusion of technology subject to export control
- If from an external vendor: 
  - Development team's point of contact
  - Copyright notices, attribution, source code for vendor modifications if needed to satisfy license obligations

> 어떤 정보를 수집해야 하나?

> FOSS의 사용법을 분석할 때, FOSS Component의 정체, 출처 및 어떤 방법으로 사용될 것인지에 대한 정보를 수집한다. 여기에는 다음 사항이 포함될 수 있다. 
- Package 이름
- Version
- 원본 Download URL
- License와 License URL
- 설명
- 수정 내용 설명
- Dependency List 
- 제품 내 사용 방법
- Package가 포함된 제품의 초도 배포일
- Source Code 입수 가능성
- Source Code를 유지할 곳
- Package가 이전 다른 환경에서 사용 승인된 적이 있는지 여부
- 수출 통제 대상 기술 포함 여부
- 외부 vendor로부터 입수한 경우,
  - 개발 팀의 연락처
  - License 의무 사항을 충족시키기 위한 저작권 고지, 귀속 정보, vendor 수정 사항에 대한 Source Code

## How do you want to use to the component?
Common scenarios include:

- Incorporation
- Linking
- Modification
- Translation

> Component를 어떻게 사용할 것인가?

> 일반적인 시나리오는 다음과 같다: 
- 통합 (Incorporation)
- Linking
- 수정 (Modification)
- 번역 (Translation)

## Incorporation

A developer may copy portions of a FOSS component into your software product. 
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/incorporation.png)

Relevant terms include:

- Integrating
- Merging
- Pasting
- Adapting
- Inserting

> 통합 (Incorporation)
개발자는 FOSS Component의 일부를 Software 제품에 복사 할 수 있다. 

> 관련 방식은 다음과 같다.:
- 통합 (Integrating)
- 병합 (Merging)
- 붙여넣기 (Pasting)
- 개작 (Adapting)
- 삽입 (Inserting)

## Linking
A developer may link or join a FOSS component with your software product. 
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/linking.png)

Relevant terms include:
- Static/Dynamic Linking
- Pairing
- Combining
- Utilizing
- Packaging
- Creating interdependency

> Linking
개발자는 FOSS Component를 Software 제품에 Link 혹은 Join할 수 있다. 

> 관련 방법은 다음과 같다: 
- 정적/동적 Linking
- Pairing
- 결합 (Combining)
- 활용 (Utilizing)
- Packaging
- 상호 의존성 만들기

## Modification
A developer may make changes to a FOSS component, including:

- Adding/injecting new code into the FOSS component
- Fixing, optimizing or making changes to the FOSS component
- Deleting or removing code
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/modification.png)

> 수정

> 개발자는 다음과 같이 FOSS Component를 수정할 수 있다. 
- FOSS Component에 새로운 Code 추가/삽입
- FOSS Component의 수정, 최적화 혹은 변경
- Code 삭제 혹은 제거

## Translation
A developer may transform the code from one state to another.
![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/translation.png)

Examples include:
- Translating Chinese to English 
- Converting C++ to Java 
- Compiling VHDL in a mask or net list
- Compiling into binary

> 번역

> 개발자는 Code를 한 상태에서 다른 상태로 변환할 수 있다. 

> 예: 
- 중국어에서 영어로 번역
- C++에서 Java로 변환
- Mask나 Net List에서 VHDL Compiling
- Binary로 Compiling

## Development Tools

Development tools may perform some of these operations behind the scenes.

![](https://github.com/hakssung/openchain-curriculum-release-1-kor/blob/master/images/developmenttools.png)

For example, a tool may inject portions of its own code into output of the tool.

> 개발 Tool

> 개발 Tool이 뒤에서 이러한 동작 중 일부를 수행할 수도 있다. 

> 예를 들어, Tool이 동작하면서 산출물 내에 자체 Code의 일부를 추가시킬 수 있다. 

## How is the FOSS component distributed?

- Who receives the software?
  - Customer/Partner
  - Community project

- What format for delivery?
  - Source code delivery
  - Binary delivery
  - Pre-loaded onto hardware

> FOSS Component는 어떻게 배포되는가?
- Software를 받는 사람은 누구인가?
  - 고객/파트너
  - Community Project
- 전달 형태는 무엇인가? 
  - Source Code 전달
  - Binary 전달
  - Hardware에 Pre-loaded

## Check Your Understanding
- What information is helpful in understanding how software is licensed?
- What information helps identify who is licensing the software?
- What is incorporation?
- What is modification?
- What is linking?
- What is translation?
- What factors are important in assessing a distribution?

> Check Your Understanding
- Software의 License가 무엇인지 이해하는데 도움이 되는 정보는 무엇인가? 
- 누가 Software에 License를 부여하는지 확인하기 위해 도움이 되는 정보는 무엇인가?
- 통합 (incorporation)이란?
- 수정 (modification)이란?
- Linking이란?
- 번역 (translation)이란?
- 배포에 대해 검토할 때 중요한 요소는 무엇인가? 
