# Guide SBOM OpenChain Telco version 1.0

Ce document est une traduction de la version originale du Guide en anglais.
En cas de divergence entre cette traduction et la version anglaise, la version anglaise prévaudra.

## 1. Portée

Ce document « Guide SBOM OpenChain Telco » vise à décrire certaines exigences liées à la façon dont une entité crée, livre et consomme des nomenclatures logicielles (SBOM), afin que les entités qui produisent et/ou consomment des SBOM conformes à ce Guide puissent garantir la répétabilité et la rationalisation des outils et des processus de génération et de consommation des SBOM. *Veuillez noter* que ce Guide n'exige pas qu'une entité conforme adopte OpenChain (dans n'importe quelle version), mais que cela est fortement encouragé.

Ce Guide est conçu pour fonctionner au niveau des SBOM : une entité peut l'utiliser comme seul moyen de fournir des SBOM, mais c'est au SBOM individuel auquel le Guide fait référence, et non à l'entité qui fournit le SBOM. Un SBOM conforme à ce Guide peut être appelé « SBOM conforme au Guide SBOM OpenChain Telco ».

La publication de SBOM qui répondent aux exigences décrites dans ce Guide n'empêche pas une entité de fournir également des SBOM pour le même logiciel sous d'autres formes ou dans d'autres formats.

Ce Guide est sous licence [Creative Commons Attribution License 4.0 (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/).

## 2. Termes et définitions

Les mots clés « DOIT », « NE DOIT PAS », « EXIGE », « DEVRAIT », « NE DEVRAIT PAS », « DEVRA », « NE DEVRA PAS », « RECOMMANDÉ »,
« PEUT » et « FACULTATIF » dans ce document sont à interpréter comme
décrit dans BCP 14 [[RFC2119]](http://abcdrfc.free.fr/rfc-vf/rfc2119.htm) [[RFC8174]](https://www.ietf.org/rfc/rfc8174.txt) si, et seulement si, ils apparaissent en majuscules, comme indiqué ici.

### Format des données
Format de données désigne le format de données des informations contenues dans le SBOM. Les formats de données possibles comprennent SPDX, CycloneDX, SWID ou d'autres formats propriétaires.

### Entité
Entité désigne l'entité juridique (à but lucratif, à but non lucratif ou personne physique) qui distribue des logiciels à des tiers (par exemple, d'autres organisations ou individus). L'entité n'inclut pas les autres sociétés du groupe ou les sociétés sous contrôle commun de l'entité.

### SBOM
Une nomenclature logicielle (SBOM, de l'anglais Software Bill of Materials) est un enregistrement formel contenant les détails et les relations dans la chaîne d'approvisionnement des divers composants utilisés dans la création de logiciels.

### Type de SBOM
Un SBOM peut être de l'un des types suivants :
* Conception,
* Source,
* Fabrication,
* Analysé,
* Déployé,
* Exécution.

La définition de ces types peut être trouvée dans le
[document CISA](https://www.cisa.gov/sites/default/files/2023-04/sbom-types-document-508c.pdf).

### SPDX
SPDX (Software Package Data Exchange) est la [norme ISO](https://www.iso.org/standard/81870.html) (ISO/CEI 5962:2021) pour l'échange de SBOM pour un logiciel donné, y compris les licences associées et les informations sur les droits d'auteur. La norme a été créée par le [projet SPDX de la Linux Foundation](https://spdx.dev/).

### OpenChain
OpenChain signifie [OpenChain ISO/CEI 5230:2020](https://www.iso.org/standard/81039.html), la norme internationale qui spécifie les exigences clés d'un programme de conformité de licence open source de qualité afin de fournir une référence qui renforce la confiance entre les organisations échangeant des solutions logicielles intégrant des logiciels open source. La norme OpenChain est produite par le [projet OpenChain](https://www.openchainproject.org) de la Linux Foundation.

### Dépendances transitives
Les dépendances transitives comprennent tous les composants nécessaires au fonctionnement du logiciel. Ils incluent toutes les dépendances du package qui ne sont pas une dépendance directe.

### Package URL (PURL)
Package URL (PURL) est une norme _de facto_ pour identifier de manière unique les packages logiciels.

## 3. Exigences

### 3.1 Format des données
Un SBOM conforme au Guide SBOM OpenChain Telco DOIT adhérer à la version 2.2 du format de données SPDX tel que normalisé dans la norme ISO/CEI 5962:2021, ou à la version 2.3 de SPDX, et comme décrit plus en détail ci-dessous en ce qui concerne les éléments inclus.

#### 3.1.1 Matériel de vérification et de référence
* ISO/CEI 5962:2021 Technologies de l'information — Spécification SPDX® V2.2.1
* [Spécification SPDX V2.3](https://spdx.github.io/spdx-spec/v2.3/)

#### 3.1.2 Justification
Pour garantir une gestion simplifiée et une rationalisation des outils et des compétences dans la chaîne d'approvisionnement des télécommunications, tant pour les fournisseurs que pour les consommateurs de logiciels, un SBOM conforme au Guide SBOM OpenChain Telco doit adhérer au format de données SPDX tel que défini dans la norme ISO/CEI 5962:2021. En harmonisant l'utilisation de ce format de données SBOM standard dans les interfaces externes d'une organisation, les complexités pour les organisations fournissant et consommant des logiciels sont simplifiées, car un seul ensemble d'exigences unifiées sera applicable.

### 3.2 Éléments SPDX à inclure dans le SBOM conforme au Guide SBOM OpenChain Telco

Les éléments suivants sont OBLIGATOIRES.

Informations sur la création de documents
* SPDXVersion : obligatoire dans SPDX
* DataLicense : obligatoire dans SPDX
* SPDXID : obligatoire dans SPDX
* DocumentName : obligatoire dans SPDX
* DocumentNamespace : obligatoire dans SPDX
* Creator : obligatoire dans SPDX
* Crated : obligatoire dans SPDX
* CreatorComment : pour pouvoir mettre le « type de SBOM »

Informations sur les packages
* PackageName : obligatoire dans SPDX
* SPDXID : obligatoire dans SPDX
* PackageVersion : requis par les « éléments minimaux d'un SBOM de la NTIA »
* PackageSupplier : requis par les « éléments minimaux d'un SBOM de la NTIA »
* PackageDownloadLocation : obligatoire dans SPDX
* FilesAnalyzed
* PackageChecksum : recommandé par « éléments minimaux d'un SBOM de la NTIA »
* PackageLicenseConcluded : obligatoire dans SPDX
* PackageLicenseDeclared : obligatoire dans SPDX
* PackageCopyrightText : obligatoire dans SPDX
* ExternalRef : pour pouvoir mettre le Package URL

Un package DEVRAIT être identifié par un Package URL (PURL).

Le PURL DEVRAIT être placé dans le champ ExternalRef, par exemple :
```
Réf externe : PACKAGE-MANAGER purl pkg:pypi/django@1.11.1
```

Relations entre les éléments SPDX
* Relation : au moins DESCRIBES et CONTAINS, nécessaires aux « éléments minimaux d'un SBOM de la NTIA »

#### 3.2.1 Matériel de vérification et de référence
« Éléments minimaux d'un SBOM de la NTIA »

#### 3.2.2 Justification
Reconnaissant le besoin d'harmonisation et d'exigences particulières du secteur des télécommunications, éventuellement au-delà des éléments minimaux de la NTIA, le « Guide SBOM OpenChain Telco » est proposé pour garantir la prévisibilité du secteur quant aux éléments attendus d'un SBOM.

Le « hachage de composant » est recommandé, mais n'est pas requis par les « éléments minimaux d'un SBOM de la NTIA ».
Dans SPDX, il correspond à PackageChecksum.
Nous le rendons obligatoire car il est important d'identifier de manière unique un package.
La plupart des outils SCA ont la capacité de produire des hachages.

Package URL (PURL) est une norme _de facto_ pour identifier de manière unique les packages logiciels.

### 3.3 Format de données lisible par machine
Le SBOM conforme au Guide SBOM OpenChain Telco DOIT inclure, au minimum, le SPDX dans l'un des formats lisible par machine suivants : Tag:Value ou JSON

#### 3.3.1 Matériel de vérification et de référence
Les formats Tag:Value et JSON sont décrits ici :
* en SPDX 2.2 https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* en SPDX 2.3 https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

#### 3.3.2 Justification
Il existe 3 formats principaux pour les SBOM : SPDX, CycloneDX et SWID.
Ces 3 formats sont ceux recommandés par le document NTIA « The Minimum Elements For a Software Bill of Materials (SBOM) » (voir section Références).

Les raisons de la sélection de SPDX comme format de données du Guide SBOM OpenChain Telco sont les suivantes :
* SPDX est une norme ISO,
* SPDX a plus de fonctionnalités que CycloneDX pour la conformité des licences,
* SPDX a un format lisible par l'homme (CycloneDX n'a que JSON et XML),
* SWID est plus un identifiant de logiciel qu'un format de SBOM à part entière.

Pour faciliter une chaîne d'outils simplifiée, une version lisible par machine du SBOM doit être incluse. Pour garantir la répétabilité et l'harmonisation, un SBOM conforme doit être au format Tag:Value ou JSON. Une entité peut publier des formats lisibles par machine supplémentaires, mais elle n'est pas tenue de se conformer au Guide.

Tag:Value est le format le plus lisible par l'homme, et il existe des convertisseurs entre les différents formats SPDX
(par exemple https://tools.spdx.org/app/convert/).

### 3.4 Format de données lisible par l'homme
Le SBOM conforme au Guide SBOM OpenChain Telco DOIT inclure, au minimum, le SPDX dans l'un des formats lisible par l'homme suivants : Tag:Value ou JSON

#### 3.4.1 Matériel de vérification et de référence
Les formats Tag:Value et JSON sont décrits ici :
* en SPDX 2.2 https://spdx.github.io/spdx-spec/v2.2.2/conformance/#44-standard-data-format-requirements
* en SPDX 2.3 https://spdx.github.io/spdx-spec/v2.3/conformance/#44-standard-data-format-requirements

#### 3.4.2 Justification
Comme le format Tag:Value est également lisible par l'homme, il a été choisi de manière à ce que les exigences d'une version standardisée lisible par machine et lisible par l'homme puissent être satisfaites à l'aide d'un seul fichier. Une entité peut publier des formats lisibles par l'homme supplémentaires, mais elles ne sont pas tenues de se conformer au Guide SBOM OpenChain Telco.

### 3.5 Informations sur la création du SBOM
Les SBOM conformes au Guide SBOM OpenChain Telco DOIVENT contenir des informations sur la date à laquelle ils ont été créés (en utilisant le champ SPDX `Created`) et sur quelle version du logiciel ils ont été créés (en utilisant le champ SPDX `CreatorComment`).

Le champ « Created » DOIT :
* contenir une ligne avec le mot-clé `Organisation` ;
* contenir une ligne avec le mot-clé `Tool` ; dans cette ligne, il DOIT y avoir après le mot-clé `Tool` le nom de l'outil et la version de l'outil.

Le nom de l'outil et la version de l'outil DEVRAIENT être séparés par un trait d'union ("-"), et aucun autre trait d'union ne DEVRAIT apparaître sur la ligne.

Les SBOM conformes au Guide SBOM OpenChain Telco DOIVENT fournir leur type de SBOM comme
[défini par CISA](https://www.cisa.gov/sites/default/files/2023-04/sbom-types-document-508c.pdf)
dans le champ `CreatorComment`.

#### 3.5.1 Matériel de vérification et de référence
Norme SPDX

#### 3.5.2 Justification
Il est important de savoir quel outil et quelle version de l'outil a créé le SBOM.

La norme SPDX donne comme exemple "toolidentifier-version", mais il n'est pas obligatoire d'avoir cette syntaxe.

Par exemple, il existe un outil qui génère :
```
Créateur : Outil : sigs.k8s.io/bom/pkg/spdx
```
Nous avons aussi:
```
Créateur : Outil : scancode-toolkit 30.1.0
```
et
```
Créateur : Outil : SCANOSS-PY : 1.5.1
```
où le nom contient un trait d'union et le nom de l'outil et la version de l'outil ne sont pas séparés par un trait d'union.

Nous ne pouvons donc pas exiger une syntaxe précise.

### 3.6 Calendrier de livraison du SBOM
Le SBOM DOIT être livré au plus tard au moment de la livraison du logiciel (sous forme binaire ou source).

#### 3.6.1 Matériel de vérification et de référence
« Éléments minimaux d'un SBOM de la NTIA », section « Distribution et livraison »

#### 3.6.2 Justification
Afin de garantir que l'entité réceptrice puisse ingérer le logiciel et son SBOM, celui-ci doit être livré au plus tard à la livraison du logiciel. Un SBOM peut être livré avant le logiciel si l'entité adoptante le souhaite, mais la livraison du logiciel doit néanmoins être accompagnée du SBOM correspondant pour garantir la conformité au Guide.

### 3.7 Méthode de livraison du SBOM
Le SBOM DOIT être intégré au logiciel lorsque cela est techniquement possible. S'il n'est pas techniquement possible d'intégrer le SBOM dans le logiciel livré, comme dans le cas de systèmes embarqués à espace limité, le fournisseur fournira une version hébergée sur le Web du SBOM qui reste disponible pendant au moins 18 mois et NE DOIT en aucun cas restreindre la capacité des destinataires à les copier et à les stocker localement pour leur propre usage. De telles restrictions NE PEUVENT PAS être imposées au destinataire dans des accords de confidentialité supplémentaires.

#### 3.7.1 Matériel de vérification et de référence
« Éléments minimaux d'un SBOM de la NTIA », section « Distribution et livraison »

#### 3.7.2 Justification
D'autres options de livraison SBOM, telles que l'hébergement Web, sont moins stables et l'accès n'est pas garanti dans le temps ; cependant, l'intégration peut ne pas être techniquement réalisable. Ainsi, dans les cas où il n'est pas possible, pour des raisons techniques, d'inclure le SBOM dans la livraison du logiciel, la publication du SBOM en ligne est autorisée à condition que le SBOM soit accessible aux destinataires du logiciel pendant 18 mois. Cette durée est conforme aux exigences de la spécification OpenChain en matière de recertification.

### 3.8 Portée du SBOM
Le SBOM DOIT contenir tous les logiciels open source fournis avec le produit, y compris toutes les dépendances transitives. Le SBOM DEVRAIT contenir tous les composants commerciaux.

Si certains composants ne sont pas inclus, ils DOIVENT être signalés comme « inconnus connus ».

#### 3.8.1 Matériel de vérification et de référence
« Éléments minimaux d'un SBOM de la NTIA », section « Inconnus connus »

#### 3.8.2 Justification
Il n'est peut-être pas possible, conseillé ou réalisable d'avoir les informations sur les composants commerciaux dans le SBOM. Il est toutefois conseillé que le SBOM soit le plus complet possible.

### 3.9 SBOM dans un déploiement SaaS
Étant donné que le Guide SBOM OpenChain Telco n'est appliqué qu'au niveau SBOM, aucune entité qui a choisi de fournir un SBOM conforme au Guide SBOM OpenChain pour certaines, voire la totalité de ses livraisons de logiciels, n'est tenue de le fournir également pour ses offres SaaS. Cependant, une entité peut choisir d'appliquer également le Guide SBOM OpenChain Telco à ses offres SaaS et ainsi fournir également le logiciel open source utilisé dans les offres SaaS avec leurs dépendances transitives en tant que SBOM.

#### 3.9.1 Matériel de vérification et de référence

#### 3.9.2 Justification
Il n'existe actuellement aucun consensus dans l'industrie sur ce que devrait contenir un SBOM SaaS.

### 3.10 SBOM pour les conteneurs
Les SBOM pour les conteneurs DEVRAIENT inclure tous les composants open source livrés dans le conteneur. Cela inclut les packages installés dans le conteneur, les composants copiés ou téléchargés dans le conteneur et les dépendances utilisées pour créer les composants compilés dans le conteneur.

#### 3.10.1 Matériel de vérification et de référence

#### 3.10.2 Justification
Chaque composant open source livré doit faire partie du SBOM.

### 3.11 Vérification du SBOM
Il est RECOMMANDÉ de fournir une signature numérique du SBOM afin de garantir l'intégrité du SBOM.

#### 3.11.1 Matériel de vérification et de référence
Sigstore https://www.sigstore.dev/ est un exemple d'une telle fonctionnalité.

#### 3.11.2 Justification
Bien que la vérification des SBOM soit un sujet important, OpenChain Telco reporte pour le moment ce travail à d'autres initiatives et a l'intention de revenir sur ce sujet dans les prochaines itérations de ce document.

### 3.12 Fusion SBOM
Les SBOM suivant ce Guide peuvent être construits à partir de plusieurs fichiers SBOM avec une relation bien définie les uns avec les autres à l'aide des fonctionnalités de définition de relation de SPDX.

#### 3.12.1 Matériel de vérification et de référence
Il existe des outils pour fusionner plusieurs SBOM en un seul, par exemple https://github.com/opensbom-generator/sbom-composer

#### 3.12.2 Justification
Il est souvent plus facile, lorsqu'il s'agit d'un produit logiciel volumineux, de fournir des SBOM individuels de ses parties plutôt qu'un seul SBOM.

### 3.13 Confidentialité SBOM
Les SBOM PEUVENT être soumis à des accords de confidentialité. Un SBOM conforme NE DOIT cependant PAS être soumis à des accords de confidentialité qui empêcheraient un destinataire de redistribuer les parties du SBOM applicables au logiciel que ce destinataire a le droit de redistribuer.

#### 3.13.1 Matériel de vérification et de référence
« Éléments minimaux d'un SBOM de la NTIA », section « Contrôle d'accès »

#### 3.13.2 Justification
Certaines licences de logiciels open source permettent à tout destinataire de redistribuer le logiciel. Dans ces situations, les destinataires devraient également être en mesure de redistribuer les parties pertinentes des SBOM.

## 4. Avis conforme
Pour indiquer que le logiciel dispose d'un SBOM conforme, vous POUVEZ utiliser la déclaration suivante : « Ce logiciel est fourni avec un SBOM conforme au Guide SBOM OpenChain Telco v1.0, le Guide est disponible sur [https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1](https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1) »

Vous POUVEZ, à votre choix, utiliser la déclaration suivante dans votre SBOM conforme au Guide SBOM OpenChain Telco : « Ce SBOM est conforme au Guide SBOM OpenChain Telco v1.0 [https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1](https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1), il est fourni gratuitement au destinataire, et le destinataire est libre de redistribuer ce SBOM à tout tiers auquel il distribue le logiciel correspondant, à condition qu'il dispose de tous les droits nécessaires pour distribuer le logiciel à ce tiers »

La déclaration suivante PEUT être utilisée comme déclaration dans un document d'appel d'offres, de commande ou le document contractuel d'un appel d'offres, de commande de développement externalisé auprès d'un fournisseur de logiciels ou de fournisseurs de systèmes de télécommunications.
« Lors de la publication d'un logiciel, il est OBLIGATOIRE de fournir un SBOM conforme au Guide SBOM OpenChain Telco v1.0 pour tous les logiciels publiés. Ce Guide est disponible sur [https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1](https://github.com/OpenChain-Project/Reference-Material/tree/master/SBOM-Quality/Version-1) »

## 5. Références

* SPDX (ISO/CEI 5962:2021)
   * https://spdx.dev/
   * https://www.iso.org/standard/81870.html
   * https://standards.iso.org/ittf/PubliclyAvailableStandards/c081870_ISO_IEC_5962_2021(E).zip
* OpenChain (ISO/CEI 5230:2020)
   * https://www.openchainproject.org/
   * https://www.iso.org/standard/81039.html
   * https://standards.iso.org/ittf/PubliclyAvailableStandards/c081039_ISO_IEC_5230_2020(E).zip
* Les éléments minimaux pour une nomenclature logicielle (SBOM), alias « éléments minimaux de la NTIA »
   * https://www.ntia.doc.gov/report/2021/minimum-elements-software-bill-materials-sbom
* Package URL (PURL)
   * https://github.com/package-url/purl-spec
