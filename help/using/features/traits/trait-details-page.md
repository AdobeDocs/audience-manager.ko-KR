---
description: 개별 트레이트에 대한 세부 정보 페이지에서는 트레이트 이름, ID, 성능 지표, 트레이트를 정의하는 표현식, 트레이트 트레이트가 속한 세그먼트 및 트레이트 감사 로그와 같은 정보를 대략적으로 제공합니다. 이러한 세부 사항을 보려면 대상 데이터 > 트레이트로 이동하여 작업할 트레이트의 이름을 클릭합니다.
seo-description: 개별 트레이트에 대한 세부 정보 페이지에서는 트레이트 이름, ID, 성능 지표, 트레이트를 정의하는 표현식, 트레이트 트레이트가 속한 세그먼트 및 트레이트 감사 로그와 같은 정보를 대략적으로 제공합니다. 이러한 세부 사항을 보려면 대상 데이터 > 트레이트로 이동하여 작업할 트레이트의 이름을 클릭합니다.
seo-title: 특성 세부 사항 페이지
solution: Audience Manager
title: 특성 세부 사항 페이지
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# 특성 세부 사항 페이지 {#trait-details-page}

개별 트레이트에 대한 세부 사항 페이지에서는 트레이트 이름, ID, 성능 지표, 트레이트를 정의하는 표현식, 트레이트 속성이 속한 세그먼트 및 트레이트 감사 로그 등 트레이트 세부 사항에 대한 개요를 제공합니다. 이러한 세부 사항을 보려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** 로 이동하여 작업할 트레이트의 이름을 클릭합니다.

## 트레이트 관리 도구 {#trait-management-tools}

트레이트 세부 정보 페이지의 맨 위에는 트레이트를 관리하는 데 사용할 수 있는 도구가 호스트됩니다.

1. **[!UICONTROL Add New]**:이 옵션을 사용하여 새로운 규칙 기반, 알고리즘 또는 온보드 트레이트를 만듭니다.
2. **[!UICONTROL Edit]**:이 옵션을 사용하여 현재 트레이트의 구성을 변경합니다.
3. **[!UICONTROL Delete]**:이 옵션을 사용하여 Audience Manager 계정에서 현재 트레이트를 제거합니다.
4. **[!UICONTROL Marketplace Recommendations]**:이 옵션을 사용하면 가입하지 않은 데이터 [!UICONTROL Audience Marketplace] 수수료로 현재 보고 있는 것과 유사한 트레이트를 찾을 수 있습니다. Marketplace [를](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) 탐색하고 유사한 트레이트를 찾는 방법은 데이터 구매자를 위한 Audience Marketplace를 참조하십시오.

![기본 특성 정보](assets/basic-trait-information.png)

## 특성 정보 {#basics}

이 [!UICONTROL Trait Information] 섹션에는 트레이트를 작성할 때 수료한 필수 필드와 선택적 필드에 대한 세부 사항이 표시됩니다. 여기에는 트레이트 유형, 트레이트 ID, 설명, 데이터 소스 및 기타 메타데이터와 같은 것들이 포함됩니다. 이러한 세부 사항은 특성 유형(폴더, 온보드 또는 규칙 기반)에 따라 달라집니다.

## 트레이트 그래프 {#trait-graph}

이 [!UICONTROL Trait Graph] 보고서는 선택한 트레이트에 대한 간략한 성능 지표를 제공합니다. 트렌드 라인 위에 커서를 두면 선택한 트레이트에 대한 추가 데이터가 표시됩니다.

[!UICONTROL Unique Trait Realizations] 주어진 시간 범위 동안 프로필에 이 트레이트를 추가한 고유한 사용자 수를 나타냅니다. 이 [!UICONTROL Total Trait Population] 트레이트에 대해 현재 자격이 있는 고유 사용자 수를 나타냅니다.

* 규칙 기반 트레이트의 경우, 사용자가 브라우저에서 트레이트를 사용할 수 있으므로 트레이트 자격은 실시간으로 발생합니다.
* 온보드 트레이트의 경우, 트레이트 자격은 인바운드 파일이 처리된 후에 발생합니다. 즉, 인바운드 파일은 Audience Manager [로](../../faq/faq-inbound-data-ingestion.md) 제공되며 이는 트레이트 자격 증명이 발생한 때입니다.
* **[!UICONTROL Unique Trait Realizations]**:지정된 시간 범위 동안 프로필에 이 트레이트를 추가한 고유한 사용자의 수입니다.
* **[!UICONTROL Total Trait Population]**:이 트레이트에 대해 현재 자격이 있는 고유 사용자 수입니다.

   ![트레이트 그래프](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**:처음 세 개의 항목에는 트레이트에 대한 자격이 가장 많은 인구 수를 가진 상위 세 개의 장치 간 데이터 소스가 내림차순으로 표시됩니다. 네 번째 항목에는 세 [!DNL DPUUIDs] 번째 항목에 포함되지 않은 장치 간 데이터 소스로부터 트레이트에 대해 자격이 부여된 다른 모든([!DNL CRM IDs])의 합계가 표시됩니다. 이 보고서는 페이지의 오른쪽 상단에 있는 [!UICONTROL Show Results By] 드롭다운 메뉴에서 장치 간 ID를 선택한 경우에만 나타납니다. 기본 드롭다운 옵션은 [!UICONTROL Device ID]이 보고서가 표시되지 않는 것입니다.

   ![트레이트 그래프](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager는 트레이트에 대해 자격이 있는 장치 간 ID가 있는 경우에만 [!UICONTROL Identity Type Breakdown] 보고서를 표시합니다.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## 특성 표현식 {#trait-expression}

이 [!UICONTROL Trait Expression] 섹션에서는 사용자가 트레이트를 얻기 위해 충족해야 하는 기준을 보여줍니다. 이러한 규칙은 트레이트를 [만들거나 편집할 때 설정됩니다](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## 트레이트 세그먼트 {#trait-segments}

이 [!UICONTROL Segments with this Trait] 섹션에는 선택한 트레이트가 속하는 모든 세그먼트가 나열됩니다. 세그먼트 이름을 클릭하여 해당 세그먼트에 대한 세부 사항을 볼 수 있습니다.

![](assets/traitSegments.png)

## 트레이트 감사/내역 로그 {#trait-audit-history}

규칙 기반 트레이트와 온보드 트레이트의 경우, 트레이트 표현식 규칙에 대한 마지막 10가지 변경 사항과 변경 사항이 [!UICONTROL Trait Expression Change History] 표시됩니다. 트레이트에 변경 사항이 10개 이상 있는 경우 클릭하여 전체 감사 로그를 **[!UICONTROL Export to CSV]** 다운로드합니다. 폴더 또는 알고리즘 특성에는 감사 로그를 사용할 수 없습니다.

>[!NOTE]
>
>[!UICONTROL Not Available] 이 [!UICONTROL By User] 열은 해당 사용자의 계정이 삭제되었음을 의미합니다.

![](assets/traitHistory.png)