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


# [!UICONTROL Trait] 세부 정보 페이지 {#trait-details-page}

개별 사용자에 대한 세부 사항 페이지는 이름, ID, 성능 지표, [!UICONTROL trait] 해당 이름을 정의하는 표현식, 해당 [!UICONTROL trait] 가 속한 세그먼트, [!UICONTROL trait] [!UICONTROL trait][!UICONTROL trait] 감사 로그 등 세부 사항에 대한 개요를 제공합니다. 이러한 세부 사항을 보려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** 로 이동하여 작업할 [!UICONTROL trait] 파일의 이름을 클릭합니다.

## [!UICONTROL Trait] 관리 도구 {#trait-management-tools}

세부 정보 페이지의 [!UICONTROL trait] 맨 위에는 사용자 관리를 위해 사용할 수 있는 도구가 호스트됩니다 [!UICONTROL traits].

1. **[!UICONTROL Add New]**: 이 옵션을 사용하여 새 [!UICONTROL rule-based]또는 [!UICONTROL algorithmic]또는 [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: 현재 구성을 변경하려면 이 옵션을 사용합니다 [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Audience Manager 계정에서 현재 항목을 제거하려면 이 옵션 [!UICONTROL trait] 을 사용합니다.
4. **[!UICONTROL Marketplace Recommendations]**: 이 옵션을 사용하면 가입하지 않은 데이터 비용 [!UICONTROL traits] 에서 현재 보고 있는 것과 유사한 내용을 찾을 수 [!UICONTROL Audience Marketplace] 있습니다. 데이터 구매자의 [Audience Marketplace에서](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) 해당 트레이트를 탐색하고 [!UICONTROL Marketplace] 유사한 트레이트를 찾는 방법을 알아보십시오.

![기본 특성 정보](assets/basic-trait-information.png)

## [!UICONTROL Trait] 정보 {#basics}

이 [!UICONTROL Trait Information] 섹션에는 작성 시 수료한 필수 필드와 선택적 필드에 대한 세부 사항이 표시됩니다 [!UICONTROL trait]. 여기에는 [!UICONTROL trait] 유형, [!UICONTROL trait] ID, 설명 [!UICONTROL data source]및 기타 메타데이터와 같은 내용이 포함됩니다. 이러한 세부 사항은 [!UICONTROL trait] 유형([!UICONTROL folder], [!UICONTROL onboarded]또는 [!UICONTROL rule-based])에 따라 다릅니다.

## [!UICONTROL Trait Graph] {#trait-graph}

이 [!UICONTROL Trait Graph] 는 선택한 항목에 대한 간략한 성능 지표를 제공합니다 [!UICONTROL trait]. 트렌드 라인 위에 커서를 두면 선택한 항목에 대한 추가 데이터가 표시됩니다 [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] 주어진 시간 범위 동안 프로필에 이 [!UICONTROL trait] 를 추가한 고유한 사용자 수를 나타냅니다. 이 [!UICONTROL Total Trait Population] 에 대해 현재 자격이 있는 고유한 사용자 수를 나타냅니다 [!UICONTROL trait].

예를 들어 [!UICONTROL rule-based traits]사용자가 브라우저에서 자격을 부여받을 때 자격 [!UICONTROL trait] 조건은 실시간으로 [!UICONTROL trait] 발생합니다.

예를 들어, [!UICONTROL onboarded traits]인바운드 파일이 처리된 후에 [!UICONTROL trait] 자격 [이 발생합니다(예: 인바운드 파일이 Audience Manager](../../faq/faq-inbound-data-ingestion.md) 로 [!UICONTROL trait] 제공되고, 이는 자격증명이 발생할 때).

다음 정보가 [!UICONTROL Trait Graph] 표시됩니다.

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: 인증된 프로필에 대한 데이터를 수집하는 결과 [!UICONTROL traits] 를 보려면 이 옵션을 선택합니다. 이 옵션을 선택하면 보고서에만 데이터가 표시되고 보고서 [!UICONTROL Cross-Device ID] 아래에는 데이터가 [!UICONTROL Device ID] 표시되지 않습니다.
   * **[!UICONTROL Device ID]**: 장치 프로파일에 대한 데이터를 수집하는 결과 [!UICONTROL traits] 를 보려면 이 옵션을 선택합니다. 이 옵션을 선택하면 보고서에만 데이터가 표시되고 보고서 [!UICONTROL Device ID] 아래에는 데이터가 [!UICONTROL Cross-Device ID] 표시되지 않습니다.

      ![트레이트 그래프](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: 지정된 시간 범위 동안 프로필에 이 [!UICONTROL trait] 를 추가한 고유한 사용자의 수입니다.
* **[!UICONTROL Total Trait Population]**: 현재 이 항목에 대해 자격이 있는 고유한 사용자 수입니다 [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: 처음 세 개의 출품작은 상위 3개 [!UICONTROL cross-device data sources] 의 인구 수가 가장 높은 상위 [!UICONTROL trait]항목을 내림차순으로 보여 줍니다. 네 번째 항목은 상위 3위 [!DNL DPUUIDs] 에 있지 않은 항목[!DNL CRM IDs]의 자격을 가진 다른 항목( [!UICONTROL trait][!UICONTROL cross-device data sources] )의 합계를 표시합니다. 이 보고서는 페이지 오른쪽 상단 [!UICONTROL Cross-device ID] 의 [!UICONTROL Show Results By] 드롭다운 메뉴에서 선택한 경우에만 나타납니다. 이 보고서가 표시되지 않는 기본 드롭다운 옵션 [!UICONTROL Device ID]은 입니다.

   ![트레이트 그래프](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager은 해당 [!UICONTROL Identity Type Breakdown] 에 [!UICONTROL cross-device] 대한 자격이 있는 경우에만 보고서를 표시합니다 [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 표현식 {#trait-expression}

이 [!UICONTROL Trait Expression] 섹션에는 사용자가 자격을 얻기 위해 충족해야 하는 기준이 표시됩니다 [!UICONTROL trait]. 이러한 규칙은 트레이트를 [만들거나 편집할 때 설정됩니다](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] 세그먼트 {#trait-segments}

이 [!UICONTROL Segments with this Trait] 섹션에는 선택한 세그먼트가 속하는 모든 세그먼트 [!UICONTROL trait] 가 나열됩니다. 세그먼트 이름을 클릭하여 해당 세그먼트에 대한 세부 사항을 볼 수 있습니다.

![](assets/traitSegments.png)

## [!UICONTROL Trait] 감사 / 기록 로그 {#trait-audit-history}

에 대해 [!UICONTROL rule-based] 와 [!UICONTROL onboarded traits]의 경우, 표현식 규칙에 대한 마지막 10개 변경 사항 [!UICONTROL Trait Expression Change History] [!UICONTROL trait] 과 변경 사항을 만든 사람을 표시합니다. 10개 [!UICONTROL trait] 이상의 변경 사항이 있는 경우 를 클릭하여 전체 감사 로그를 **[!UICONTROL Export to CSV]** 다운로드합니다. 감사 로그는 [!UICONTROL folder] 또는 에서 사용할 수 없습니다 [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] 열에서 [!UICONTROL By User] 는 해당 사용자의 계정이 삭제되었음을 의미합니다.

![](assets/traitHistory.png)