---
description: 개별 트레이트에 대한 세부 정보 페이지에서는 특성 이름, ID, 성능 지표, 트레이트를 정의하는 표현식, 트레이트가 속한 세그먼트, 트레이트 감사 로그 등의 정보에 대한 개요를 제공합니다. 이러한 세부 사항을 보려면 대상 데이터 > 트레이트로 이동하고 작업할 트레이트의 이름을 클릭합니다.
seo-description: 개별 트레이트에 대한 세부 정보 페이지에서는 특성 이름, ID, 성능 지표, 트레이트를 정의하는 표현식, 트레이트가 속한 세그먼트, 트레이트 감사 로그 등의 정보에 대한 개요를 제공합니다. 이러한 세부 사항을 보려면 대상 데이터 > 트레이트로 이동하고 작업할 트레이트의 이름을 클릭합니다.
seo-title: 트레이트 세부 사항 페이지
solution: Audience Manager
title: 트레이트 세부 사항 페이지
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# [!UICONTROL Trait] 세부 정보 페이지  {#trait-details-page}

개별 [!UICONTROL trait]에 대한 세부 정보 페이지는 [!UICONTROL trait] 세부 정보에 대한 개요를 제공합니다. 예를 들어 [!UICONTROL trait] 이름, ID, 성능 지표, [!UICONTROL trait]을(를) 정의하는 표현식, 해당 세그먼트가 속한 세그먼트 및 [!UICONTROL trait] 감사 로그가 있습니다. 이러한 세부 사항을 보려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]**&#x200B;로 이동하고 작업할 [!UICONTROL trait]의 이름을 클릭합니다.

## [!UICONTROL Trait] 관리 도구  {#trait-management-tools}

[!UICONTROL trait] 세부 정보 페이지의 맨 위에는 [!UICONTROL traits]을(를) 관리하는 데 사용할 수 있는 도구가 호스트됩니다.

1. **[!UICONTROL Add New]**:이 옵션을 사용하여 새  [!UICONTROL rule-based]또는  [!UICONTROL algorithmic]또는 [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**:현재 구성을 변경하려면 이 옵션을 사용합니다 [!UICONTROL trait].
3. **[!UICONTROL Delete]**:Audience Manager 계정 [!UICONTROL trait] 에서 현재 항목을 제거하려면 이 옵션을 사용합니다.
4. **[!UICONTROL Marketplace Recommendations]**:이 옵션을 사용하면 가입하지 않은  [!UICONTROL traits] 데이터 비용 [!UICONTROL Audience Marketplace] 에서 현재 보고 있는 것과 유사한 내용을 찾을 수 있습니다. ](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)을(를) 탐색하고 유사한 특성을 찾는 방법을 알려면 데이터 구매자 Audience Marketplace[을(를) 참조하십시오.[!UICONTROL Marketplace]

![기본 특성 정보](assets/basic-trait-information.png)

## [!UICONTROL Trait] 정보 {#basics}

[!UICONTROL Trait Information] 섹션에는 [!UICONTROL trait]을(를) 빌드할 때 수료한 필수 필드와 선택적 필드에 대한 세부 사항이 표시됩니다. 여기에는 [!UICONTROL trait] 유형, [!UICONTROL trait] ID, 설명, [!UICONTROL data source] 및 기타 메타데이터와 같은 항목이 포함됩니다. 이러한 세부 사항은 [!UICONTROL trait] 유형([!UICONTROL folder], [!UICONTROL onboarded] 또는 [!UICONTROL rule-based])에 따라 다릅니다.

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]은 선택한 [!UICONTROL trait]에 대한 간략한 성능 지표를 제공합니다. 트렌드 라인 위에 커서를 두면 선택한 [!UICONTROL trait]에 대한 추가 데이터가 표시됩니다.

[!UICONTROL Unique Trait Realizations] 지정된 시간 범위 동안 프로필에 이 [!UICONTROL trait] 를 추가한 고유한 사용자 수를 나타냅니다. [!UICONTROL Total Trait Population]은 현재 이 [!UICONTROL trait]에 대해 자격이 있는 고유한 사용자의 수를 나타냅니다.

[!UICONTROL rule-based traits]의 경우, 사용자가 브라우저에서 [!UICONTROL trait]의 자격이 부여되므로 실시간으로 자격 증명이 수행됩니다.[!UICONTROL trait]

[!UICONTROL onboarded traits]의 경우, 인바운드 파일이 처리된 후에 [!UICONTROL trait] 자격이 발생합니다(예: 인바운드 파일은 [Audience Manager](../../faq/faq-inbound-data-ingestion.md)으로 제공됨). 즉 [!UICONTROL trait] 자격이 발생하는 때입니다.

[!UICONTROL Trait Graph]에 다음 정보가 표시됩니다.

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**:인증된 프로필의 데이터를 수집하는 결과 [!UICONTROL traits] 를 보려면 이 옵션을 선택합니다. 이 옵션을 선택하면 [!UICONTROL Cross-Device ID] 보고서에만 데이터가 표시되고 [!UICONTROL Device ID] 보고서 아래에는 데이터가 없습니다.
   * **[!UICONTROL Device ID]**:장치 프로파일에 대한 데이터를 수집하는 결과 [!UICONTROL traits] 를 보려면 이 옵션을 선택합니다. 이 옵션을 선택하면 [!UICONTROL Device ID] 보고서에만 데이터가 표시되고 [!UICONTROL Cross-Device ID] 보고서 아래에는 데이터가 없습니다.

      ![트레이트 그래프](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**:지정된 시간 범위 동안 프로필 [!UICONTROL trait] 에 이 항목을 추가한 고유한 사용자 수입니다.
* **[!UICONTROL Total Trait Population]**:현재 이 항목에 대해 자격이 있는 고유한 사용자 수입니다 [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**:처음 세 개의 출품작은 상위 세 개 [!UICONTROL cross-device data sources] 의 인구 수가 가장 높은 상위  [!UICONTROL trait]항목을 내림차순으로 보여 줍니다. 네 번째 항목은 상위 3개 항목에 없는 [!UICONTROL cross-device data sources]에서 [!UICONTROL trait]에 대해 자격이 있는 다른 모든 [!DNL DPUUIDs]([!DNL CRM IDs])의 합계를 표시합니다. 이 보고서는 페이지의 오른쪽 상단에 있는 [!UICONTROL Show Results By] 드롭다운 메뉴에서 [!UICONTROL Cross-device ID]을 선택한 경우에만 나타납니다. 기본 드롭다운 옵션은 [!UICONTROL Device ID]이며, 여기서 이 보고서는 표시되지 않습니다.

   ![트레이트 그래프](assets/trait-identity.png)

   >[!NOTE]
   >
   >[!UICONTROL trait]에 대해 자격이 있는 [!UICONTROL cross-device] ID가 있는 경우 Audience Manager은 [!UICONTROL Identity Type Breakdown] 보고서만 표시합니다.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 표현식 {#trait-expression}

[!UICONTROL Trait Expression] 섹션에는 사용자가 [!UICONTROL trait]의 자격을 얻기 위해 충족해야 하는 기준이 표시됩니다. 이러한 규칙은 [트레이트](../../features/traits/about-trait-builder.md)를 만들거나 편집할 때 설정됩니다.

![](assets/traitExpression.png)

## [!UICONTROL Trait] 세그먼트 {#trait-segments}

[!UICONTROL Segments with this Trait] 섹션에는 선택한 [!UICONTROL trait]이(가) 속하는 모든 세그먼트가 나열됩니다. 세그먼트 이름을 클릭하여 해당 세그먼트에 대한 세부 사항을 볼 수 있습니다.

![](assets/traitSegments.png)

## [!UICONTROL Trait] 감사 / 기록 로그  {#trait-audit-history}

[!UICONTROL rule-based] 및 [!UICONTROL onboarded traits]의 경우 [!UICONTROL Trait Expression Change History]는 [!UICONTROL trait] 식 규칙에 대해 수행한 마지막 10개의 변경 사항을 보여 줍니다. [!UICONTROL trait]에 변경 내용이 10개 이상 있는 경우 **[!UICONTROL Export to CSV]**&#x200B;을 클릭하여 전체 감사 로그를 다운로드합니다. 감사 로그는 [!UICONTROL folder] 또는 [!UICONTROL algorithmic traits]에 사용할 수 없습니다.

>[!NOTE]
>
>[!UICONTROL Not Available] 이  [!UICONTROL By User] 열에서 해당 사용자의 계정이 삭제되었음을 의미합니다.

![](assets/traitHistory.png)