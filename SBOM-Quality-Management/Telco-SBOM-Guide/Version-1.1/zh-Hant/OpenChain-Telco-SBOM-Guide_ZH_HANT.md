# OpenChain 電信 SBOM 指引 版本 1.1

本文是英文的翻譯版本。如果此翻譯與英文原文之間存在任何差異，則以英文原文為準。

## 1. 範圍

本文件「OpenChain 電信 SBOM 指引」目的為概述實體如何建立、交付及使用軟體物料清單（SBOM）的相關要求，確保符合本指引的實體在產生及使用 SBOM 時，能實現工具與流程的重複性和高效化。請注意，本指引不要求符合的實體必須採用任何版本的 OpenChain，但我們強烈建議採用。

此指引設計為針對單一 SBOM：實體可將其作為傳遞 SBOM 的唯一方式，但指引針對的是個別 SBOM，而非提供該 SBOM 的實體。依據本指引的 SBOM 可稱為「符合 OpenChain 電信 SBOM 指引」。

發佈符合本指引要求的 SBOM 並不妨礙實體以其他方式或格式傳遞相同軟體的 SBOM。

本指引採用 [創用 CC 姓名標示 4.0 國際 (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/) 授權條款。

## 2. 術語與定義
本文件中的關鍵詞 「必須 (MUST)」、「禁止 (MUST NOT)」、「需要 (REQUIRED)」、「應 (SHALL)」、「不得 (SHALL NOT)」、「應該 (SHOULD)」、「不應該 (SHOULD NOT)」、「建議 (RECOMMENDED)」、「不建議 (NOT RECOMMENDED)」、「可以 (MAY)」及「可選 (OPTIONAL)」，應依據 BCP 14 [[RFC2119]](https://www.ietf.org/rfc/rfc2119.txt)  [[RFC8174]](https://www.ietf.org/rfc/rfc8174.txt)  的定義進行解釋，且僅當這些詞語完全以大寫形式出現時適用。

### 資料格式
資料格式指 SBOM 中資訊的格式。可能的資料格式包括 SPDX、CycloneDX、SWID 或其他專有格式。

### 實體
「實體」指散佈軟體給第三方（如其他組織或個人）的法人組織（營利或非營利）或自然人。不包括其他集團公司，也不包括受該實體共同控制的公司。

### SBOM
軟體物料清單（SBOM）是包含用於構建軟體的各組件詳細資訊及供應鏈關係的正式記錄。

### SBOM 類型
SBOM 可為以下類型之一：
* 設計（Design）、
* 原始碼（Source）、
* 構建（Build）、
* 分析（Analyzed）、
* 部署（Deployed）、
* 運行（Runtime）。

這些類型的定義可見
[CISA document](https://www.cisa.gov/sites/default/files/2023-04/sbom-types-document-508c.pdf).

### SPDX
SPDX (Software Package Data Exchange) 是 [ISO standard](https://www.iso.org/standard/81870.html) (ISO/IEC 5962:2021)，用於交換軟體包的 SBOM，包括相關的授權和版權資訊。此標準由 [Linux Foundation's SPDX project](https://spdx.dev/) 建立.

### OpenChain
OpenChain 指 [OpenChain ISO/IEC 5230:2020](https://www.iso.org/standard/81039.html), 此國際標準規範高品質開源授權合規計畫的關鍵要求，為交換含開源軟體的解決方案的組織之間建立信任基準。該標準由 Linux Foundation 的 [OpenChain project](https://www.openchainproject.org) 制定.

### 傳遞性依賴
傳遞性依賴指軟體運行所需的所有組件，包括任何非直接依賴的套件。

### 套件 URL (PURL)
套件 URL (PURL) 是一個事實標準，用於唯一識別軟體套件。

## 3. 要求

### 3.1 資料格式
符合 OpenChain 電信 SBOM 指引的文件應遵循 ISO/IEC 5962:2021 標準的 SPDX 資料格式第 2.2 版，或標準第 2.3 版，並根據以下描述包含必要元素。

#### 3.1.1 驗證與參考資料
* ISO/IEC 5962:2021 資訊技術 — SPDX® 規範第 2.2.1 版
* [SPDX Specification V2.3](https://spdx.github.io/spdx-spec/v2.3/)

#### 3.1.2 說明
為簡化電信供應鏈中供應商和軟體消費者的工具和流程，符合 OpenChain 電信 SBOM 指引的文件應採用 ISO/IEC 5962:2021 標準化的 SPDX 資料格式。透過統一 SBOM 資料格式，供應商和使用者的工具和流程可以簡化，僅需遵循一致的要求，從而減少複雜性。

實體可自由選擇替代資料格式用於內部用途，或根據需求向組織提供其他格式的 SBOM。本指引僅適用於 SBOM 文件，而非整個組織。

### 3.2 適用於 OpenChain 電信 SBOM 指引文件的 SPDX 元素內容

需要包含以下元素。

文件生成資訊
* SPDXVersion: SPDX 中的強制項目
* DataLicense: SPDX 中的強制項目
* SPDXID: SPDX 中的強制項目
* DocumentName: SPDX 中的強制項目
* DocumentNamespace: SPDX 中的強制項目
* Creator: SPDX 中的強制項目
* Created: SPDX 中的強制項目
* CreatorComment: 填寫 “SBOM 建立資訊”

套件資訊
* PackageName: SPDX 中的強制項目
* SPDXID: SPDX 中的強制項目
* PackageVersion: “NTIA SBOM 最小元素” 必要項目
* PackageSupplier: “NTIA SBOM 最小元素” 必要項目
* PackageDownloadLocation: SPDX 中的強制項目
* PackageLicenseConcluded: SPDX 2.2 中的強制項目
* PackageLicenseDeclared: SPDX 2.2 中的強制項目
* PackageCopyrightText: SPDX 2.2 中的強制項目

建議使用 PackageChecksum 或 PackageVerificationCode 其中一個屬性：
由 “NTIA SBOM 最小元素” 建議

軟體包應該使用 套件 URL (PURL) 進行識別。若有提供 PURL，則應該填寫於 ExternalRef 欄位，例如：

```
ExternalRef: PACKAGE-MANAGER purl pkg:pypi/django@1.11.1
```

SPDX 元素之間的關係
* Relationship: 至少需要描述並包含 “NTIA SBOM 最小元素” 必要項目

#### 3.2.1 驗證與參考資料
NTIA SBOM 最小元素

#### 3.2.2 說明
考慮到電信行業的調和需求及特定要求，“OpenChain 電信 SBOM 指引” 目的在為行業提供可預期的 SBOM 元素標準。

“元件雜湊值” 是建議項目，但不是 “NTIA SBOM 最小元素” 的強制要求。在 SPDX 中對應到 PackageChecksum 或者 PackageVerificationCode。大多數 SCA 工具均具有生成雜湊值的功能。

CISA 文件 "軟體元件透明性框架：建立通用的軟體物料清單（SBOM）第三版"
https://www.cisa.gov/resources-tools/resources/framing-software-component-transparency-2024
允許同時使用這兩種屬性，詳見第 2.5 節中的表格。

Package URL (PURL) 是唯一識別軟體包的事實標準。

### 3.3 機器可讀的資料格式
符合 OpenChain 電信 SBOM 指引的文件應包括至少以下之一的 SPDX 機器可讀格式：Tag:Value 或 JSON。

#### 3.3.1 驗證與參考資料
Tag:Value 和 JSON 格式的描述見以下連結：
* 在 SPDX 2.2 https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* 在 SPDX 2.3 https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

#### 3.3.2 說明
目前 SBOM 的主要格式有三種：SPDX、CycloneDX 和 SWID。
這三種格式被 NTIA 文件《軟體物料清單 (SBOM) 最小元素》中推薦（請參閱「5. 參考資料」部分）。

選擇 SPDX 作為 OpenChain 電信 SBOM 指引的資料格式的原因包括：
* SPDX 是 ISO 標準；
* SPDX 在合規授權方面比 CycloneDX 具有更多功能；
* SPDX 具有人類可閱讀的格式（CycloneDX 僅支持 JSON 和 XML）；
* SWID 更像是軟體識別碼，而非完整的 SBOM 格式。

為簡化工具鏈，SBOM 必須包含機器可讀的版本，以確保一致性和可重現性。符合本指引的 SBOM 必須採用 Tag:Value 或 JSON 格式。
實體可以釋出額外的機器可讀格式，但這些額外格式不要求符合 (NOT REQUIRED TO CONFORM TO) 本指引

Tag:Value 是最適合人類閱讀的格式，並且可使用各種工具相互轉換不同的 SPDX 格式，例如：
(https://tools.spdx.org/app/convert/). JSON 格式 是許多工具所產生的標準格式.

### 3.4 人類可讀的資料格式
符合 OpenChain 電信 SBOM 指引的文件，至少應以人類可讀之格式提供 SPDX，其格式須為 Tag:Value 或 JSON 之一。

#### 3.4.1 驗證與參考資料
Tag:Value 和 JSON 格式的描述見以下連結：
* 在 SPDX 2.2 https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* 在 SPDX 2.3 https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

#### 3.4.2 說明
由於 Tag:Value 格式也可被人類閱讀，因此選擇該格式以同時滿足標準化的機器可讀和人類可讀版本的需求。

### 3.5 SBOM 資訊建立
符合 OpenChain 電信 SBOM 指引的 SBOM 必須包含其建立時間（使用 SPDX Created 欄位）以及其所對應的軟體版本（使用 SPDX CreatorComment 欄位）。

`Creator` 欄位必須：
* 包含一行 `Organization` 關鍵字，標示 SBOM 建立的組織。
* 包含一行 `Tool `關鍵字，標示 SBOM 生成工具及其版本。該行必須以「工具名稱-工具版本」格式表示，且不得包含額外的連字符號（"-"）。

符合 OpenChain 電信 SBOM 指引的 SBOM 應該在 CreatorComment 欄位中標示其 SBOM 類型，該類型應依據
[CISA 定義](https://www.cisa.gov/sites/default/files/2023-04/sbom-types-document-508c.pdf)

建議使用以下語法標示 SBOM 類型：“SBOM Type: xxx”，其中 “xxx” 應為以下六個關鍵字之一：“Design”、“Source”、“Build”、“Analyzed”、“Deployed” 及 “Runtime”。

#### 3.5.1 驗證與參考資料
SPDX 標準

#### 3.5.2 說明
了解產生 SBOM 的工具及其版本相當重要。

SPDX 標準提供了"toolidentifier-version" 作為範例，但並未強制要求使用此語法。

例如，某些工具的輸出格式如下：
```
Creator: Tool: sigs.k8s.io/bom/pkg/spdx
```
或:
```
Creator: Tool: scancode-toolkit 32.3.0
```
以及:
```
Creator: Tool: SCANOSS-PY: 1.18.1
```
其中部分工具名稱包含連字符號，且工具名稱與版本並未使用連字符號區分。

因此，本指引不強制要求特定的語法格式。

CreatorComment 是自由文字欄位。我們使用此欄位來儲存 CISA SBOM 類型，因為在 SPDX 2.2 和 2.3 中尚未提供專用欄位，但當然也可存放其他資訊。

我們不強制特定的格式，只要求至少包含下列六個關鍵字之一：“Design”、“Source”、“Build”、“Analyzed”、“Deployed”、“Runtime”，大小寫不限。

因此，以下範例皆有效，並且建議使用第一個範例：
```
CreatorComment: SBOM Type: Deployed
```
```
CreatorComment: Analyzed
```
```
CreatorComment: This SBOM was created during build phase.
```

### 3.6 SBOM 交付時間
SBOM 應於軟體交付時（無論是二進位或原始碼形式）或之前交付。

#### 3.6.1 驗證與參考資料
“NTIA SBOM 最小元素”, 章節 “Distribution and Delivery”

#### 3.6.2 說明
為確保接收實體方能夠正確接收軟體及其 SBOM，SBOM 應至少於軟體交付時提供。

若採用實體方選擇，SBOM 可以在軟體交付前提供，但軟體交付時仍必須隨附對應的 SBOM，以確保符合本指引的要求。

### 3.7 SBOM 交付方式
SBOM 應於在技術可行的情況下嵌入至軟體 “套件” 中。
若技術上無法將 SBOM 嵌入至交付的軟體套件（例如，受儲存空間限制的嵌入式系統），供應方應提供 至少可存取 18 個月的線上托管 (web-hosted) SBOM 版本，並且不得限制接收方複製或本地儲存 SBOM 以供自身使用。

此外，此類限制不得透過額外的保密協議強加於接收方。

#### 3.7.1 驗證與參考資料
“NTIA SBOM 最小元素”, 章節 “Distribution and Delivery”

#### 3.7.2 說明
相較於內嵌式 SBOM，網頁托管 SBOM 的存取穩定性較低，且無法保證可被長期存取；然而，內嵌 SBOM 在某些技術場景下可能無法實現。

因此，當技術上無法將 SBOM 內嵌至軟體交付時，可透過線上方式提供 SBOM，前提是 SBOM 至少應該可供軟體接收方存取 18 個月。

此存取時限符合 OpenChain 標準對於再驗證(Recertification)的要求。

### 3.8 SBOM 範圍
SBOM 應包含產品交付時的所有開源軟體 (Open Source Software)，包括所有傳遞性依賴 (Transitive Dependencies)。

SBOM 應該包含所有商業元件 (Commercial Components)。

若部分元件未納入 SBOM，則必須註明為「已知但未包含的元件 (Known Unknowns)」。

#### 3.8.1 驗證與參考資料
“NTIA SBOM 最小元素”, 章節 section “Known Unknowns”

#### 3.8.2 說明
某些商業元件可能因技術、法規或商業考量，無法納入SBOM；即便如此，SBOM 應該儘可能完整，以確保可追溯性和合規性。

### 3.9 SaaS 環境中的 SBOM
由於 OpenChain 電信 SBOM 指引僅適用於 SBOM 層級，選擇提供符合 OpenChain 電信 SBOM 指引的文件之實體，無需 (NO REQUIREMENT) 針對其 SaaS 服務交付 SBOM。

然而，實體可以選擇適用本指引於其 SaaS 服務，並提供 SaaS 服務中使用之開源軟體及其傳遞性依賴的 SBOM。

#### 3.9.1 驗證與參考資料

#### 3.9.2 說明
目前業界對於 SaaS 環境中的 SBOM 應包含哪些內容尚未達成共識。

### 3.10 容器的 SBOMs
容器的 SBOMs 應該包含隨容器交付的所有開源元件，包括安裝於容器內的軟體套件、複製或下載至容器的元件，以及用於構建容器內編譯元件的所有依賴項。

#### 3.10.1 驗證與參考資料

#### 3.10.2 說明
所有交付的開源元件都應納入 SBOMs，以確保完整性和可追溯性。

### 3.11 SBOM 驗證
建議提供 SBOM 的數位簽章，以確保 SBOM 的完整性。

#### 3.11.1 驗證與參考資料
Sigstore https://www.sigstore.dev/ 是可用的數位簽章方案之一。

#### 3.11.2 說明
雖然 SBOMs 的驗證機制相當重要，但 OpenChain 電信 SBOM 指引目前將此議題交由其他專案處理，並計畫在未來版本中進一步探討。

### 3.12 SBOM 合併
依據本指引的 SBOMs 可由多個 SBOM 文件組成，並透過 SPDX 的關聯定義功能 (Relationship Definition) 來描述其關聯性。

#### 3.12.1 驗證與參考資料
有許多工具可提供多個 SBOM 文件合併，例如 https://github.com/interlynk-io/sbomasm

#### 3.12.2 說明
對於大型軟體產品而言，將其拆分為多個 SBOM 文件通常比提供單一完整 SBOM 更易於管理。

### 3.13 SBOM 保密性
SBOM 可以受保密協議 (Confidentiality Agreements) 的約束。

然而，符合本指引的 SBOM 不得遭受任何限制，導致接收方無法重新散佈 SBOM 中與開源軟體相關的部分。

#### 3.13.1 驗證與參考資料
“NTIA SBOM 最小元素”, 章節 section “Access Control”

#### 3.13.2 說明
某些開源軟體授權允許接收方重新散佈軟體。在這些情況下，接收方應該也能夠重新散佈相應的 SBOM 部分。

## 4. 符合性聲明
為表明軟體包含符合本指引的 SBOM，可使用以下聲明：“此軟體附有符合 OpenChain 電信 SBOM 指引 v1.1 的 SBOM，該指引可於 [https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md) 取得”

亦可選擇在符合 OpenChain 電信 SBOM 指引的 SBOM 中使用以下聲明：“此 SBOM 符合 OpenChain 電信 SBOM 指引 v1.1 [https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md)，免費提供給接收方，接收方可自由將此 SBOM 散佈給任何第三方，前提是接收方擁有散佈該軟體至此第三方的一切必要權利。”

此外，當向軟體供應商或電信系統供應商提交 RFP、採購訂單或外包開發合約時，可在文件中使用以下聲明：“釋出軟體時，供應方需要提供符合 OpenChain 電信 SBOM 指引 v1.1 的 SBOM。該指引可於 [https:
//github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md](https://github.com/OpenChain-Project/Telco-WG/blob/main/OpenChain-Telco-SBOM-Guide_EN.md) 取得。

## 5. 參考資料

* SPDX (ISO/IEC 5962:2021)
  * https://spdx.dev/
  * https://www.iso.org/standard/81870.html
  * https://standards.iso.org/ittf/PubliclyAvailableStandards/c081870_ISO_IEC_5962_2021(E).zip
  * SPDX Specification V2.3: https://spdx.github.io/spdx-spec/v2.3/
* OpenChain (ISO/IEC 5230:2020)
  * https://www.openchainproject.org/
  * https://www.iso.org/standard/81039.html
  * https://standards.iso.org/ittf/PubliclyAvailableStandards/c081039_ISO_IEC_5230_2020(E).zip
* 軟體物料清單 (SBOM) 最小元素 又稱 “NTIA 最小元素”
  * https://www.ntia.doc.gov/report/2021/minimum-elements-software-bill-materials-sbom
* 軟體元件透明性框架：建立通用的軟體物料清單（SBOM）第三版
  * https://www.cisa.gov/resources-tools/resources/framing-software-component-transparency-2024
* 套件 URL (PURL)
  * https://github.com/package-url/purl-spec

## 6. 指引修訂歷史

本指引於 1.1 版進行了以下更新：

* 同時允許使用 PackageChecksum 和 PackageVerificationCode 作為套件雜湊值。
* 套件雜湊值從強制項目調整為建議。
* ExternalRef 從強制項目調整為建議。
* FilesAnalyzed 不再是強制項目。
* 提供了 CISA SBOM 類型的範例。
* 提供了 CISA SBOM 類型的建議語法。
* sbomasm 是一個更適合作為 SBOM 合併工具的範例。
* 新增對最新 CISA 文件的參考。

符合本指引 1.0 版的 SBOM 文件亦符合 1.1 版的要求，但反之則不成立。
