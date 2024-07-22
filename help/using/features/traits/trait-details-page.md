---
description: 개별 트레이트에 대한 세부 정보 페이지에서는 트레이트 이름, ID, 성능 지표, 트레이트를 정의하는 표현식, 트레이트가 속한 세그먼트 및 트레이트 감사 로그와 같은 정보에 대한 개요를 제공합니다. 이러한 세부 정보를 보려면 대상 데이터 > 트레이트 로 이동하여 작업할 트레이트의 이름을 클릭합니다.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: 트레이트 세부 사항 페이지
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: id 유형 분류, id 분류, 대상 id 보고, 교차 장치, 교차 장치 ID, 장치 ID
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# [!UICONTROL Trait] 세부 정보 페이지 {#trait-details-page}

개별 [!UICONTROL trait]에 대한 세부 정보 페이지에서는 [!UICONTROL trait] 이름, ID, 성능 지표, [!UICONTROL trait]을(를) 정의하는 표현식, 해당 세그먼트가 속한 세그먼트, [!UICONTROL trait] 감사 로그와 같은 [!UICONTROL trait] 세부 정보에 대한 개요를 제공합니다. 이러한 세부 정보를 보려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]**(으)로 이동하여 작업할 [!UICONTROL trait]의 이름을 클릭합니다.

## [!UICONTROL Trait] 관리 도구 {#trait-management-tools}

[!UICONTROL trait] 세부 정보 페이지의 상단에는 [!UICONTROL traits]을(를) 관리하는 데 사용할 수 있는 도구가 호스팅됩니다.

1. **[!UICONTROL Add New]**: 새 [!UICONTROL rule-based], [!UICONTROL algorithmic] 또는 [!UICONTROL onboarded traits]을(를) 만들려면 이 옵션을 사용합니다.
2. **[!UICONTROL Edit]**: 이 옵션을 사용하여 현재 [!UICONTROL trait]의 구성을 변경합니다.
3. **[!UICONTROL Delete]**: 이 옵션을 사용하여 Audience Manager 계정에서 현재 [!UICONTROL trait]을(를) 제거합니다.
4. **[!UICONTROL Marketplace Recommendations]**: 이 옵션을 사용하면 구독하지 않은 데이터 요금 [!UICONTROL Audience Marketplace]에서 현재 보고 있는 것과 유사한 [!UICONTROL traits]을(를) 찾을 수 있습니다. [!UICONTROL Marketplace]을(를) 탐색하고 유사한 트레이트를 찾는 방법에 대해 알아보려면 [데이터 구매자용 Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)를 참조하십시오.

![기본 특성 정보](assets/basic-trait-information.png)

## [!UICONTROL Trait] 정보 {#basics}

[!UICONTROL Trait Information] 섹션에는 [!UICONTROL trait]을(를) 빌드할 때 완료한 필수 및 선택적 필드에 대한 세부 정보가 표시됩니다. 여기에는 [!UICONTROL trait] 형식, [!UICONTROL trait] ID, 설명, [!UICONTROL data source] 및 기타 메타데이터와 같은 항목이 포함됩니다. 이러한 세부 정보는 [!UICONTROL trait] 유형([!UICONTROL folder], [!UICONTROL onboarded] 또는 [!UICONTROL rule-based])에 따라 다릅니다.

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]은(는) 선택한 [!UICONTROL trait]에 대한 성능 지표를 한눈에 제공합니다. 선택한 [!UICONTROL trait]에 대한 추가 데이터를 보려면 추세선 위에 커서를 놓습니다.

[!UICONTROL Unique Trait Realizations]은(는) 지정된 시간 범위 동안 프로필에 이 [!UICONTROL trait]을(를) 추가한 고유 사용자 수를 나타냅니다. [!UICONTROL Total Trait Population]은(는) 현재 이 [!UICONTROL trait]에 대해 자격이 있는 고유 사용자의 수를 나타냅니다.

[!UICONTROL rule-based traits]의 경우 사용자가 브라우저에서 [!UICONTROL trait]에 대한 자격을 얻을 때 [!UICONTROL trait] 자격이 실시간으로 발생합니다.

[!UICONTROL onboarded traits]의 경우 [!UICONTROL trait] 자격은 인바운드 파일이 처리된 후에 발생합니다. 즉, 인바운드 파일이 [Audience Manager에 제공됨](../../faq/faq-inbound-data-ingestion.md)이며, 이는 [!UICONTROL trait] 자격이 발생한 때입니다.

[!UICONTROL Trait Graph]에는 다음 정보가 표시됩니다.

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: 인증된 프로필에 대한 데이터를 수집하는 [!UICONTROL traits]의 결과를 보려면 이 옵션을 선택하십시오. 이 옵션을 선택하면 [!UICONTROL Cross-Device ID] 보고서의 데이터만 표시되고 [!UICONTROL Device ID] 보고서 아래에 데이터가 표시되지 않습니다.
   * **[!UICONTROL Device ID]**: 장치 프로필에 대한 데이터를 수집하는 [!UICONTROL traits]의 결과를 보려면 이 옵션을 선택하십시오. 이 옵션을 선택하면 [!UICONTROL Device ID] 보고서의 데이터만 표시되고 [!UICONTROL Cross-Device ID] 보고서 아래에 데이터가 표시되지 않습니다.

     ![특성 그래프](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: 지정된 시간 범위 동안 프로필에 이 [!UICONTROL trait]을(를) 추가한 고유 사용자 수입니다.
* **[!UICONTROL Total Trait Population]**: 현재 이 [!UICONTROL trait]에 대해 자격이 있는 고유 사용자 수입니다.

* **[!UICONTROL Identity Type Breakdown]**: 처음 세 항목은 [!UICONTROL trait]에 적합한 모집단 수가 가장 많은 상위 세 개의 [!UICONTROL cross-device data sources]을(를) 내림차순으로 표시합니다. 네 번째 항목은 [!UICONTROL trait]에 대해 자격이 있는 다른 모든 [!DNL DPUUIDs]([!DNL CRM IDs])과(와) 상위 3에 없는 [!UICONTROL cross-device data sources]의 합계를 보여줍니다. 이 보고서는 페이지 오른쪽 상단의 [!UICONTROL Show Results By] 드롭다운 메뉴에서 [!UICONTROL Cross-device ID]을(를) 선택한 경우에만 나타납니다. 기본 드롭다운 옵션은 [!UICONTROL Device ID]이며, 여기에는 이 보고서가 표시되지 않습니다.

  ![특성 그래프](assets/trait-identity.png)

  >[!NOTE]
  >
  >Audience Manager은 [!UICONTROL trait]에 적합한 ID가 [!UICONTROL cross-device]개인 경우에만 [!UICONTROL Identity Type Breakdown] 보고서를 표시합니다.

  >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 식 {#trait-expression}

[!UICONTROL Trait Expression] 섹션에는 사용자가 [!UICONTROL trait]에 대한 자격을 얻기 위해 충족해야 하는 기준이 표시됩니다. 이러한 규칙은 [특성을 만들거나 편집](../../features/traits/about-trait-builder.md)할 때 설정됩니다.

![](assets/traitExpression.png)

## [!UICONTROL Trait] 세그먼트 {#trait-segments}

[!UICONTROL Segments with this Trait] 섹션에는 선택한 [!UICONTROL trait]이(가) 속한 모든 세그먼트가 나열됩니다. 세그먼트 이름을 클릭하여 해당 세그먼트에 대한 세부 정보를 볼 수 있습니다.

![](assets/traitSegments.png)

## [!UICONTROL Trait] 감사/기록 로그 {#trait-audit-history}

[!UICONTROL rule-based] 및 [!UICONTROL onboarded traits]의 경우 [!UICONTROL Trait Expression Change History]은(는) [!UICONTROL trait] 식 규칙에 대한 마지막 10가지 변경 내용과 변경한 사람을 표시합니다. [!UICONTROL trait]에 10개가 넘는 변경 내용이 있는 경우 **[!UICONTROL Export to CSV]**&#x200B;을(를) 클릭하여 전체 감사 로그를 다운로드합니다. [!UICONTROL folder] 또는 [!UICONTROL algorithmic traits]에 대해 감사 로그를 사용할 수 없습니다.

>[!NOTE]
>
>[!UICONTROL By User] 열의 [!UICONTROL Not Available]은(는) 해당 사용자의 계정이 삭제되었음을 의미합니다.

![](assets/traitHistory.png)
