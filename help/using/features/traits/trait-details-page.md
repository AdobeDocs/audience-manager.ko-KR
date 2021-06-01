---
description: 개별 트레이트에 대한 세부 사항 페이지에서는 트레이트 이름, ID, 성능 지표, 트레이트를 정의하는 표현식, 트레이트가 속한 세그먼트 및 트레이트 감사 로그와 같은 정보에 대한 개요를 제공합니다. 이러한 세부 사항을 보려면 대상 데이터 > 트레이트 로 이동하고 작업하려는 트레이트의 이름을 클릭합니다.
seo-description: 개별 트레이트에 대한 세부 사항 페이지에서는 트레이트 이름, ID, 성능 지표, 트레이트를 정의하는 표현식, 트레이트가 속한 세그먼트 및 트레이트 감사 로그와 같은 정보에 대한 개요를 제공합니다. 이러한 세부 사항을 보려면 대상 데이터 > 트레이트 로 이동하고 작업하려는 트레이트의 이름을 클릭합니다.
seo-title: 트레이트 세부 사항 페이지
solution: Audience Manager
title: 트레이트 세부 사항 페이지
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: id 유형 분류, ID 분류, 대상 ID 보고, 교차 장치, 교차 장치 ID, 장치 ID
feature: 트레이트
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# [!UICONTROL Trait] 세부 사항 페이지  {#trait-details-page}

개별 [!UICONTROL trait]에 대한 세부 정보 페이지에서는 [!UICONTROL trait] 이름, ID, 성능 지표, [!UICONTROL trait]을 정의하는 표현식, 해당 세그먼트가 속한 세그먼트 및 [!UICONTROL trait] 감사 로그와 같은 세부 정보에 대한 개요를 제공합니다. [!UICONTROL trait] 이러한 세부 사항을 보려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** 로 이동하여 작업하려는 [!UICONTROL trait] 이름을 클릭합니다.

## [!UICONTROL Trait] 관리 도구  {#trait-management-tools}

[!UICONTROL trait] 세부 정보 페이지의 맨 위에는 [!UICONTROL traits] 관리 시 사용할 수 있는 도구가 호스팅됩니다.

1. **[!UICONTROL Add New]**:이 옵션을 사용하여 새  [!UICONTROL rule-based],  [!UICONTROL algorithmic]또는  [!UICONTROL onboarded traits]을 만듭니다.
2. **[!UICONTROL Edit]**:현재 구성을 변경하려면 이 옵션을 사용합니다  [!UICONTROL trait].
3. **[!UICONTROL Delete]**:이 옵션을 사용하여 Audience Manager 계정 [!UICONTROL trait] 에서 현재 계정을 제거합니다.
4. **[!UICONTROL Marketplace Recommendations]**:이 옵션을 사용하면 구독하지  [!UICONTROL traits] 않은  [!UICONTROL Audience Marketplace] 데이터 요금에서 현재 보고 있는 것과 유사한 내용을 찾을 수 있습니다. [!UICONTROL Marketplace]를 탐색하고 유사한 트레이트를 찾는 방법을 알려면 데이터 구매자용 [Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)을 참조하십시오.

![기본 트레이트 정보](assets/basic-trait-information.png)

## [!UICONTROL Trait] 정보 {#basics}

[!UICONTROL Trait Information] 섹션에는 [!UICONTROL trait] 작성 시 완료한 필수 및 선택적 필드에 대한 세부 정보가 표시됩니다. 여기에는 [!UICONTROL trait] 유형, [!UICONTROL trait] ID, 설명, [!UICONTROL data source] 및 기타 메타데이터와 같은 것들이 포함됩니다. 이러한 세부 사항은 [!UICONTROL trait] 유형([!UICONTROL folder], [!UICONTROL onboarded] 또는 [!UICONTROL rule-based])에 따라 다릅니다.

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]은(는) 선택한 [!UICONTROL trait]에 대한 성과 지표를 한 눈에 알려줍니다. 꺾은 선형 위에 커서를 놓으면 선택한 [!UICONTROL trait]에 대한 추가 데이터가 표시됩니다.

[!UICONTROL Unique Trait Realizations] 지정된 시간 범위 동안 프로필에 이 [!UICONTROL trait] 를 추가한 고유 사용자 수를 나타냅니다. [!UICONTROL Total Trait Population] 은 이 [!UICONTROL trait]에 대해 현재 자격이 있는 고유한 사용자 수를 나타냅니다.

[!UICONTROL rule-based traits]의 경우 사용자가 브라우저에서 [!UICONTROL trait]에 대한 자격이 부여되므로 [!UICONTROL trait] 자격이 실시간으로 발생합니다.

[!UICONTROL onboarded traits]의 경우 인바운드 파일이 처리된 후 [!UICONTROL trait] 자격이 발생합니다. 즉, 인바운드 파일이 [Audience Manager](../../faq/faq-inbound-data-ingestion.md)에 입력되었으며, 그 때는 [!UICONTROL trait] 자격이 발생합니다.

[!UICONTROL Trait Graph]에 다음 정보가 표시됩니다.

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**:인증된 프로필에 대한 데이터를 수집하는  [!UICONTROL traits] 결과를 보려면 이 옵션을 선택합니다. 이 옵션을 선택하면 [!UICONTROL Cross-Device ID] 보고서에만 데이터가 표시되고 데이터가 [!UICONTROL Device ID] 보고서 아래에 표시되지 않습니다.
   * **[!UICONTROL Device ID]**:장치 프로필에 대한 데이터를 수집하는 결과 [!UICONTROL traits] 를 보려면 이 옵션을 선택합니다. 이 옵션을 선택하면 [!UICONTROL Device ID] 보고서에만 데이터가 표시되고 데이터가 [!UICONTROL Cross-Device ID] 보고서 아래에 표시되지 않습니다.

      ![트레이트 그래프](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**:지정된 시간 범위 동안 프로필 [!UICONTROL trait] 에 이 정보를 추가한 고유 사용자 수입니다.
* **[!UICONTROL Total Trait Population]**:현재 이 항목에 대해 자격이 있는 고유 사용자 수입니다 [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**:처음 세 항목은 내림차순으로  [!UICONTROL cross-device data sources] 자격이 있는 상위 세 개 [!UICONTROL trait]를 보여줍니다. 네 번째 항목에는 상위 3개 항목에 없는 [!UICONTROL cross-device data sources]에서 [!UICONTROL trait]에 대해 자격이 있는 다른 모든 [!DNL DPUUIDs]([!DNL CRM IDs])의 합계가 표시됩니다. 이 보고서는 페이지의 오른쪽 상단에 있는 [!UICONTROL Show Results By] 드롭다운 메뉴에서 [!UICONTROL Cross-device ID]을 선택하는 경우에만 나타납니다. 기본 드롭다운 옵션은 [!UICONTROL Device ID] 이며, 이 보고서는 표시되지 않습니다.

   ![트레이트 그래프](assets/trait-identity.png)

   >[!NOTE]
   >
   >[!UICONTROL trait]에 대해 자격이 있는 [!UICONTROL cross-device] ID가 있는 경우에만 Audience Manager에 [!UICONTROL Identity Type Breakdown] 보고서가 표시됩니다.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 표현식 {#trait-expression}

[!UICONTROL Trait Expression] 섹션에는 사용자가 [!UICONTROL trait]에 대한 자격을 얻기 위해 충족해야 하는 기준이 표시됩니다. 이러한 규칙은 [트레이트](../../features/traits/about-trait-builder.md)를 만들거나 편집할 때 설정됩니다.

![](assets/traitExpression.png)

## [!UICONTROL Trait] 세그먼트 {#trait-segments}

[!UICONTROL Segments with this Trait] 섹션에는 선택한 [!UICONTROL trait]이 속한 모든 세그먼트가 나열됩니다. 세그먼트 이름을 클릭하여 해당 세그먼트에 대한 세부 사항을 볼 수 있습니다.

![](assets/traitSegments.png)

## [!UICONTROL Trait] 감사/내역 로그  {#trait-audit-history}

[!UICONTROL rule-based] 및 [!UICONTROL onboarded traits]의 경우 [!UICONTROL Trait Expression Change History]에 [!UICONTROL trait] 표현식 규칙에 수행된 마지막 10개의 변경 사항이 표시되고 사용자가 이를 만들었습니다. [!UICONTROL trait]에 10개 이상의 변경 사항이 있는 경우 **[!UICONTROL Export to CSV]**&#x200B;을 클릭하여 전체 감사 로그를 다운로드합니다. 감사 로그는 [!UICONTROL folder] 또는 [!UICONTROL algorithmic traits]에 사용할 수 없습니다.

>[!NOTE]
>
>[!UICONTROL Not Available] 열 [!UICONTROL By User] 에서 은(는) 해당 사용자의 계정이 삭제되었음을 의미합니다.

![](assets/traitHistory.png)
