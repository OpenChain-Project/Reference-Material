# OpenChain Telco SBOM Guide Version 1.0

本书是英文文本的译本。如果本翻译与英文版本之间存在任何差异，则以英文版本为准。

## 1. 范围

本文“OpenChain Telco SBOM Guide”旨在概括实体如何创建、分发和消费物料清单(SBOM)相关的某些要求,以便生产和(或)消费符合本指南的SBOM的实体，可以确保生成和消费SBOM的工具和流程可重复性和精简性。*请注意*本指南不要求符合条件的实体采用Openchain（在任何版本中），但非常鼓励这样做。

本指南旨在适用于每个SBOM级别：实体可以将其用作交付SBOM的唯一方式，但指南所指的是单个SBOM，而不是提供SBOM的实体。使用本指南的SBOM可以称为“OpenChain Telco SBOM Guide兼容”。

发布符合本指南中概述的要求的SBOM并不排除使用其他替代方式或格式为同一软件提供SBOM。

本指南的许可证是[Creative Commons Attribution License 4.0 (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/)

## 2. 术语和定义

本文关键词 "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
      NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED",
      "MAY", and "OPTIONAL" 应解释为BCP 14 [[RFC2119]](https://www.ietf.org/rfc/rfc2119.txt)  [[RFC8174]](https://www.ietf.org/rfc/rfc8174.txt)中的描述，当且仅当他们出现在所有大写字母中，如下所示。

## 数据格式

数据格式是指SBOM中信息的数据格式。可能的数据格式包括SPDX、Cyclone DX、SWID或者其他专有格式。

### 实体

实体应指向分发软件到第三方（例如，其他组织或个人）的法务主体（营利性、非营利性或自然人）。实体不包括其他集团公司或者实体共同控制的公司。

### SBOM

物料清单（SBOM）是一种正式记录，包括构建软件使用的各种组件的详细信息和供应链关系。

### SBOM 类型

SBOM可以是以下类型之一：
* Design,
* Source,
* Build,
* Analyzed,
* Deployed,
* Runtime.

这些类型的定义可以在[CISA document](https://www.cisa.gov/sites/default/files/2023-04/sbom-types-document-508c.pdf)找到。

### SPDX

SPDX (Software Package Data Exchange) 是[ISO standard](https://www.iso.org/standard/81870.html) (ISO/IEC 5962:2021) 用于交换给定软件包的SBOM，包括关联的许可证和版权信息。该标准由[Linux Foundation's SPDX project](https://spdx.dev/)创建。

### OpenChain

OpenChain是指[OpenChain ISO/IEC 5230:2020](https://www.iso.org/standard/81039.html)，该国际标准规定了高质量开源许可证合规程序的关键要求，以便提供基准，在交换包含开源软件的软件解决方案的组织之间建立信任。OpenChain标准是由Linux基金会[OpenChain project](https://www.openchainproject.org)制定。

### 传递依赖

传递依赖是软件运行所必须的所有组件。他们包括包的任何非直接依赖的依赖项。

### 包URL（PURL）

包URL（PURL）是一个唯一标识软件包的 _事实标准_。

## 3. 要求

### 3.1 数据格式

一个“OpenChain Telco SBOM Guide 兼容”文档应该遵守ISO/IEC 5962:2021中标准化的SPDX数据格式2.2版或者标准2.3版，如下文描述中关于所包括的元素。

#### 3.1.1 校验和参考材料

* ISO/IEC 5962:2021 Information technology — SPDX® Specification V2.2.1
* [SPDX Specification V2.3](https://spdx.github.io/spdx-spec/v2.3/)

#### 3.1.2 理由

为了确保通信供应商中工具和能力的简化处理和精简，OpenChain Telco SBOM Guide兼容文档应遵守ISO/IEC 5962:2021中标准化的SPDX数据格式。通过协调组织外部接口中标准SBOM数据格式的使用，简化了提供和消费软件的组织的复杂性，因为只有一组统一要求适用。

作为澄清，实体可以自由在内部使用替代数据格式，或者使用替代数据格式向有要求或主动(要求)的组织分发SBOM。OpenChain Telco SBOM Guide指南是一个需要遵守的SBOM级别规范，而不是一个需要遵守的组织规范。没有符合要求的实体，只有符合要求的SBOM，由实施OpenChain Telco SBOM Guide指南的实体提供。

### 3.2 包含OpenChain Telco SBOM Guide兼容文档中的SPDX元素

需要以下元素。

文档创建信息
* SPDXVersion: SPDX必填项目
* DataLicense: SPDX必填项目
* SPDXID: SPDX必填项目
* DocumentName: SPDX必填项目
* DocumentNamespace: SPDX必填项目
* Creator: SPDX必填项目
* Created: SPDX必填项目
* CreatorComment: 能够放入“SBOM构建信息”

包信息
* PackageName: SPDX必填项目
* SPDXID: SPDX必填项目
* PackageVersion: “NTIA SBOM 最小必须元素”需要
* PackageSupplier: “NTIA SBOM 最小必须元素”需要
* PackageDownloadLocation: SPDX必填项目
* FilesAnalyzed
* PackageChecksum: “NTIA SBOM 最小必须元素”推荐填写
* PackageLicenseConcluded: SPDX必填项目
* PackageLicenseDeclared: SPDX必填项目
* PackageCopyrightText: SPDX必填项目
* ExternalRef: 能够放入PURL

包建议（SHOULD）由包URL（PURL）标识。

PURL建议（SHOULD）放在ExternalRef字段中，例如。
```
ExternalRef: PACKAGE-MANAGER purl pkg:pypi/django@1.11.1
```

SPDX元素之间的关系
* 关系：至少描述和包含，“NTIA SBOM 最小必须元素“需要

#### 3.2.1 校验和参考资料
NTIA 最小必须元素

#### 3.2.2 理由

鉴于通信行业需要协调和特殊要求，可能超过NTIA最小必须元素，提出了“OpenChain Telco SBOM Guide”指南，以确保行业对预期SBOM元素的可预测性。

建议使用“组件哈希”，但是“NTIA SBOM 最小必须元素“不需要。
在SPDX中，它映射到PackageChecksum。
我们将其设为强制性，因为唯一标识一个包非常重要。
大多数SCA工具都有能力提供哈希值。

包URL（PURL）是唯一标识软件包的 _事实标准_

### 3.3 机器可读数据格式

OpenChain Telco SBOM兼容文档应至少包括以下机器可读格式之一的SPDX：Tag:Value 或者 JSON。


#### 3.3.1 校验和参考资料

这里描述Tag:Value 和 JSON格式：
* in SPDX 2.2 https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* in SPDX 2.3 https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

#### 3.3.2 理由

有3种主要的SBOM格式：SPDX、CycloneDX和SWID。
这3种格式是NTIA文档"The Minimum Elements For a Software Bill of Materials (SBOM)"（参阅参考资料部分）推荐的格式。

选择SPDX作为OpenChain Telco SBOM Guide指南的数据格式原因如下：
* SPDX是ISO标准,
* SPDX在许可证合规方面比CycloneDX具有更多功能,
* SPDX具有人类可读格式(CycloneDX只有JSON和XML格式),
* SWID与其说是一种成熟的SBOM格式，不如说是一种软件标识符.

为了简化工具链，需要包括机器可读的SBOM版本。为了确保可重复性和协调，符合标准的SBOM必须采用Tag:Value或者JSON格式。实体可以发布其他机器可读格式，不要求符合此指南。

Tag:Value是人类最容易阅读的格式，各种SPDX格式之间有转换器（例如，https://tools.spdx.org/app/convert/） 。JSON是由多个工具生成的格式。

### 3.4 人类可读数据格式
OpenChain Telco SBOM 兼容文档应（SHALL）至少包含以下机器可读格式之一的SPDX：Tag:Value或JSON。

#### 3.4.1 校验和参考资料

这里描述Tag:Value和JSON格式：
* SPDX 2.2 https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* SPDX 2.3 https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

#### 3.4.2 理由

由于Tag:Value格式也是人类可读，因此选择它是为了使用一个文件可以同时满足标准化机器可读和人类可读版本要求。实体可以发布额外的人类可读格式，不需要符合OpenChain Telco SBOM Guide指南。

### 3.5 SBOM构建信息

符合OpenChain Telco SBOM Guide指南的SBOM必须（MUST）要包含创建时间（使用SPDX`Created`字段）和创建他们软件版本的信息（使用SPDX`CreatorComment`字段）

`Creator`字段必须（MUST）：
* 包含`Organization`关键字的行;
* 包含`Tool`关键字的行；在这一行中，我们必须（MUST）在`Tool`关键字后面加上工具名称和工具版本。

工具名称和工具版本应当以连字符("-")分隔，该行不能出现其他连字符。

符合OpenChain Telco SBOM Guide指南的SBOM必须（MUST）提供SBOM类型为[defined by CISA](https://www.cisa.gov/sites/default/files/2023-04/sbom-types-document-508c.pdf)定义的`CreatorComment`字段中。

#### 3.5.1 校验和参考资料

SPDX标准

#### 3.5.2 理由

了解创建SBOM的工具以及版本很重要。

SPDX标准提供了"toolidentifier-version"作为一个例子，但并不强制要求有这种语法。

例如，有一个工具可以输出：
```
Creator: Tool: sigs.k8s.io/bom/pkg/spdx
```
我们还有
```
Creator: Tool: scancode-toolkit 30.1.0
```
和
```
Creator: Tool: SCANOSS-PY: 1.5.1
```
其中名称包含连字符，工具名和版本不用连字符分隔。

所以我们不能要求精确的语法。

### 3.6 SBOM交付时间

SBOM应当（SHALL）不迟于交付软件时交付（以二进制或源码形式）

#### 3.6.1 校验和参考材料

“NTIA SBOM Minimum elements”，“Distribution and Delivery”部分

#### 3.6.2 理由

为了确保接收实体接收软件及其SBOM，应不迟于软件交付时交付。如果接收实体要求，SBOM可以在软件交付之前交付，但是软件交付时必须附有相应的SBOM，以确保符合指南。

### 3.7 SBOM的交付方式

如果技术可行的话，SBOM应（SHALL）当嵌入软件“包”。如果在交付时嵌入软件“包”技术上不可行，例如在一个空间受限的嵌入式系统情况下，供应方应提供至少18个月可用的SBOM的网络托管版本，并且不应（SHALL NOT）以任何方式限制接收方在本地复制和存储这些版本以供自己使用。此类限制不得（MAY NOT）在额外的保密协议中对接收方施加。

#### 3.7.1 校验和参考资料

“NTIA SBOM Minimum elements”，“Distribution and Delivery”部分

#### 3.7.2 理由

其他SBOM交付的选项，例如虚拟主机稳定性差，长期无法保证可访问性；然而“embedding”嵌入可能技术不可行。因此，在技术上无法将SBOM包含在软件交付中的情况下，只要求将SBOM在线发布18个月，以便软件接收者可访问。这个期间符合OpenChain specification规范对重新认证的要求。

### 3.8 SBOM范围

SBOM应（SHALL）包含随软件交付的所有开源软件，包括所有传递依赖。SBOM建议（SHOULD）包含所有的商业组件。

如果一些组件未包含，则必须（MUST）将其报告为“known unknowns.”

#### 3.8.1 校验和参考材料

“NTIA SBOM Minimum elements”, “Known Unknowns”部分

#### 3.8.2 理由

在SBOM中包含商业组件信息可能是不可能、不可取或者不可行的。但是，建议SBOM尽可能保持完整。

### 3.9 SaaS部署中的SBOM

由于OpenChain Telco SBOM Guide指南仅用于SBOM级别，因此选择为其部分甚至全部软件交付提供OpenChain Telco SBOM Compatible兼容文档的实体，不需要为其SaaS产品提供此文档。然而，实体可以选择将OpenChain Telco SBOM Guide指南也应用于其SaaS产品，从而将SaaS产品中使用的开源软件与其传递依赖作为SBOM交付。

#### 3.9.1 校验和参考资料

#### 3.9.2 理由

目前业界对SaaS SBOM应该包含什么没有共识。

### 3.10 容器的SBOM

容器的SBOM应（SHOULD）包括容器交付的所有的开源组件。这个包括容器中安装的包、拷贝或下载的组件以及在容器中用于构建编译组件使用的依赖。

#### 3.10.1 校验和参考资料

#### 3.10.2 理由
交付的每个开源组件都应该是SBOM的一部分。

### 3.11 SBOM校验

为了保证SBOM的完整性，建议（RECOMMENDED）提供SBOM的数字签名。

#### 3.11.1 校验和参考资料

Sigstore https://www.sigstore.dev/ 就是这种能力的一个例子。

#### 3.11.2 理由

尽管SBOM验证是一个重要话题，OpenChain Telco目前将这项工作推迟到其他计划，并打算在本文档的未来重新审视这个话题。

### 3.12 SBOM合并

遵循本指南的SBOM可以使用SPDX中的关系定义功能，从多个彼此之间有明确定义关系的SBOM文件里构建

#### 3.12.1 校验和参考资料

存在多种工具将多个SBOM合并成一个，例如 https://github.com/opensbom-generator/sbom-composer

#### 3.12.2 理由

在处理大型软件产品时，提供其部分的单个SBOM通常比整体SBOM更容易。

### 3.13 SBOM 保密

SBOM可能（MAY）受到保密协议的约束。然而，符合要求的SBOM必须不（MUST NOT）受到任何保密协议的约束，这些协议会阻止接收方重新分发适用于该接收方有权重新分发的软件的SBOM部分。


#### 3.13.1 校验和参考资料

“NTIA SBOM Minimum elements”，“Access Control”部分

#### 3.13.2 理由

一些开源的软件许可证允许任何接收者重新分发软件。在这些情况下，接收者还应该能够重新分发SBOM的相关部分。


## 4. Conformant notice

## 4. 合规声明

为了表明该软件有符合标准的SBOM可用，您可以（MAY）使用如下声明。“该软件附带符合OpenChain Telco SBOM Guide v1.0的SBOM，该指南可在[https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1](https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1)获取”

您可以（MAY）选择在您的电信指南中使用符合SBOM的以下声明“此SBOM符合OpenChain Telco SBOM Guide v1.0 [https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1](https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1)，它是免费提供给接收者，并且接收者可以自由的将此SBOM重新分发给他们分发相应软件的任何第三方，前提是他们拥有将软件分发给此类第三方的所有必要权利”

当向软件供应商或电信系统供应商请求RFP、采购订单或者外包开发订单时，以下声明可用作RFP文档、订单文档或者合同文档中的声明。“发布软件时，必须（REQUIRED）为所有发布的软件提供符合OpenChain Telco SBOM Guide v1.0的SBOM。指南可在 [https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1](https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1)获取”

## 5. 参考资料

* SPDX (ISO/IEC 5962:2021)
  * https://spdx.dev/
  * https://www.iso.org/standard/81870.html
  * https://standards.iso.org/ittf/PubliclyAvailableStandards/c081870_ISO_IEC_5962_2021(E).zip
  * SPDX Specification V2.3: https://spdx.github.io/spdx-spec/v2.3/
* OpenChain (ISO/IEC 5230:2020)
  * https://www.openchainproject.org/
  * https://www.iso.org/standard/81039.html
  * https://standards.iso.org/ittf/PubliclyAvailableStandards/c081039_ISO_IEC_5230_2020(E).zip
* The Minimum Elements For a Software Bill of Materials (SBOM) a.k.a. “NTIA minimum elements”
  * https://www.ntia.doc.gov/report/2021/minimum-elements-software-bill-materials-sbom
* Package URL (PURL)
  * https://github.com/package-url/purl-spec
