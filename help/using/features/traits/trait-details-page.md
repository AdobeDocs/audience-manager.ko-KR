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
source-wordcount: '614'
ht-degree: 0%

---

# [!UICONTROL Trait] 세부 정보 페이지 {#trait-details-page}

개인에 대한 세부 정보 페이지 [!UICONTROL trait] 의 개요를 제공합니다. [!UICONTROL trait] 세부 정보(예: ) [!UICONTROL trait] 다음을 정의하는 이름, ID, 성능 지표, 표현식 [!UICONTROL trait], 세그먼트가 속하고, [!UICONTROL trait] 감사 로그. 이러한 세부 정보를 보려면 다음 위치로 이동하십시오. **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** 이름을 클릭합니다. [!UICONTROL trait] 함께 작업하고 싶으신 거군요.

## [!UICONTROL Trait] 관리 도구 {#trait-management-tools}

의 맨 위 [!UICONTROL trait] 세부 정보 페이지는 를 관리하는 데 사용할 수 있는 도구를 호스팅합니다. [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: 이 옵션을 사용하여 새로 만듭니다 [!UICONTROL rule-based], [!UICONTROL algorithmic], 또는 [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: 이 옵션을 사용하여 현재 구성을 변경합니다 [!UICONTROL trait].
3. **[!UICONTROL Delete]**: 이 옵션을 사용하여 현재 [!UICONTROL trait] Audience Manager 계정에서.
4. **[!UICONTROL Marketplace Recommendations]**: 유사한 항목 찾기 이 옵션 사용 [!UICONTROL traits] 지금 보고 있는 사람 [!UICONTROL Audience Marketplace] 구독하지 않은 데이터 요금입니다. 다음을 참조하십시오 [데이터 구매자용 Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) 탐색 방법을 알아보려면 [!UICONTROL Marketplace] 유사한 트레이트를 찾아보십시오.

![기본 트레이트 정보](assets/basic-trait-information.png)

## [!UICONTROL Trait] 정보 {#basics}

다음 [!UICONTROL Trait Information] 섹션에는 빌드를 수행할 때 완료한 필수 및 선택적 필드에 대한 세부 정보가 표시됩니다. [!UICONTROL trait]. 여기에는 다음과 같은 항목이 포함됩니다. [!UICONTROL trait] 유형, [!UICONTROL trait] ID, 설명, [!UICONTROL data source]및 기타 메타데이터 이러한 세부 사항은 다음에 따라 다릅니다 [!UICONTROL trait] 유형([!UICONTROL folder], [!UICONTROL onboarded], 또는 [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

다음 [!UICONTROL Trait Graph] 은(는) 선택한 항목에 대한 성능 지표를 한눈에 제공합니다. [!UICONTROL trait]. 선택한 항목에 대한 추가 데이터를 보려면 트렌드 라인 위에 커서를 놓습니다. [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] 이 항목을 추가한 고유 사용자 수를 나타냅니다. [!UICONTROL trait] 지정된 시간 범위 동안 프로필에 매핑합니다. 다음 [!UICONTROL Total Trait Population] 현재 이에 적합한 고유 사용자 수를 나타냅니다. [!UICONTROL trait].

대상 [!UICONTROL rule-based traits], [!UICONTROL trait] 자격 부여는 사용자가 다음에 대한 자격을 갖출 때 실시간으로 수행됩니다. [!UICONTROL trait] 브라우저에 표시됩니다.

대상 [!UICONTROL onboarded traits], [!UICONTROL trait] 검증은 인바운드 파일이 처리된 후 발생합니다(예: 인바운드 파일: [Audience Manager에 제공됨](../../faq/faq-inbound-data-ingestion.md) 그리고 그 때가 [!UICONTROL trait] 자격이 발생합니다.

다음 [!UICONTROL Trait Graph] 다음 정보를 표시합니다.

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: 다음에 대한 결과를 보려면 이 옵션을 선택합니다. [!UICONTROL traits] 인증된 프로필에 대한 데이터를 수집하고 있습니다. 이 옵션을 선택하면 [!UICONTROL Cross-Device ID] 보고서 및 아래에 데이터가 없습니다. [!UICONTROL Device ID] 보고서.
   * **[!UICONTROL Device ID]**: 다음에 대한 결과를 보려면 이 옵션을 선택합니다. [!UICONTROL traits] 장치 프로필에 대한 데이터를 수집하는 중입니다. 이 옵션을 선택하면 [!UICONTROL Device ID] 보고서 및 아래에 데이터가 없습니다. [!UICONTROL Cross-Device ID] 보고서.

      ![특성 그래프](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: 이 항목을 추가한 고유 사용자 수 [!UICONTROL trait] 지정된 시간 범위 동안 프로필에 매핑합니다.
* **[!UICONTROL Total Trait Population]**: 현재 이에 적합한 고유 사용자 수 [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: 처음 세 항목은 상위 3개를 보여 줍니다 [!UICONTROL cross-device data sources] 을(를) 위해 자격을 얻은 가장 높은 모집단 수로 [!UICONTROL trait]내림차순으로 정렬됩니다. 네 번째 항목은 다른 모든 항목의 합계를 보여 줍니다 [!DNL DPUUIDs] ([!DNL CRM IDs])에 적합한 [!UICONTROL trait], [!UICONTROL cross-device data sources] 상위 3개에는 없습니다. 이 보고서는 다음을 선택하는 경우에만 나타납니다. [!UICONTROL Cross-device ID] 다음에서 [!UICONTROL Show Results By] 페이지 오른쪽 상단의 드롭다운 메뉴. 기본 드롭다운 옵션은 입니다. [!UICONTROL Device ID]: 이 보고서가 표시되지 않는 경우입니다.

   ![특성 그래프](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager은 [!UICONTROL Identity Type Breakdown] 다음을 보유한 경우 보고 [!UICONTROL cross-device] 에 적합한 ID [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 표현식 {#trait-expression}

다음 [!UICONTROL Trait Expression] 섹션에는 사용자가 다음에 대한 자격을 얻기 위해 충족해야 하는 기준이 표시됩니다. [!UICONTROL trait]. 다음 규칙은 다음과 같은 경우에 설정됩니다. [트레이트 만들기 또는 편집](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] 세그먼트 {#trait-segments}

다음 [!UICONTROL Segments with this Trait] 섹션에는 선택한 모든 세그먼트가 나열됩니다. [!UICONTROL trait] 이(가)에 속합니다. 세그먼트 이름을 클릭하여 해당 세그먼트에 대한 세부 정보를 볼 수 있습니다.

![](assets/traitSegments.png)

## [!UICONTROL Trait] 감사/내역 로그 {#trait-audit-history}

대상 [!UICONTROL rule-based] 및 [!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History] 에 대한 마지막 10개 변경 사항을 표시합니다. [!UICONTROL trait] 표현식 규칙 및 만든 사람. 다음의 경우 [!UICONTROL trait] 이(가) 10개 이상의 변경 사항을 가지고 있습니다. **[!UICONTROL Export to CSV]** 전체 감사 로그를 다운로드합니다. 감사 로그를 다음에 사용할 수 없습니다. [!UICONTROL folder] 또는 [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] 다음에서 [!UICONTROL By User] 열은 해당 사용자의 계정이 삭제되었음을 의미합니다.

![](assets/traitHistory.png)
