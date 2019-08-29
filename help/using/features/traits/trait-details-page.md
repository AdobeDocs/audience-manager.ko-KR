---
description: 개별 트레이트에 대한 세부 사항 페이지는 트레이트 이름, ID, 성능 지표, 트레이트, 트레이트 및 트레이트 감사 로그에 속하는 표현식의 개요를 제공합니다. 이러한 세부 사항을 보려면 대상 데이터 > 트레이트로 이동하여 작업할 트레이트 이름을 클릭합니다.
seo-description: 개별 트레이트에 대한 세부 사항 페이지는 트레이트 이름, ID, 성능 지표, 트레이트, 트레이트 및 트레이트 감사 로그에 속하는 표현식의 개요를 제공합니다. 이러한 세부 사항을 보려면 대상 데이터 > 트레이트로 이동하여 작업할 트레이트 이름을 클릭합니다.
seo-title: 특성 세부 사항 페이지
solution: Audience Manager
title: 특성 세부 사항 페이지
uuid: 23301376-C 1 CC -4778-B 8 C 4-9831 F 6739 DB 9
translation-type: tm+mt
source-git-commit: aadcafe10d452a0abc02a430485a373c6c80cdc5

---


# 특성 세부 사항 페이지 {#trait-details-page}

개별 트레이트에 대한 세부 사항 페이지는 트레이트 이름, ID, 성능 지표, 트레이트, 트레이트 및 트레이트 감사 로그에 속하는 표현식의 개요를 제공합니다. 이러한 세부 사항을 보려면 [!UICONTROL Audience Data > Traits] 작업할 트레이트 이름을 클릭하여 클릭합니다.

## 기본 정보 {#basics}

[!UICONTROL Basic Information] 이 섹션에는 트레이트를 빌드할 때 완료한 필수 필드와 선택적 필드에 대한 세부 사항이 표시됩니다. 특성 유형, 특성 ID, 설명, 데이터 소스 및 기타 메타데이터와 같은 것들이 포함됩니다. 이러한 세부 사항은 특성 유형 (폴더, 온보드 또는 규칙 기반) 에 따라 다릅니다.

![](assets/basicInfo.png)

## 트레이트 그래프 {#trait-graph}

는 [!UICONTROL Trait Graph] 선택한 트레이트에 대해 한 눈에 볼 수 있는 성능 지표를 제공합니다. 트렌드 라인 위에 커서를 두면 선택한 트레이트에 대한 추가 데이터가 표시됩니다.

[!UICONTROL Unique Trait Realizations] 주어진 시간 범위에서 프로필에 이 트레이트를 추가한 고유한 사용자의 수를 나타냅니다. 는 이 트레이트에 대해 현재 자격 조건을 갖춘 고유한 사용자 수를 [!UICONTROL Total Trait Population] 나타냅니다.

* 규칙 기반의 트레이트에 대해 사용자가 브라우저에서 트레이트를 적용받을 수 있으므로 트레이트 자격 조건은 실시간으로 발생합니다.
* 온보딩된 트레이트에 대한 트레이트 자격 조건은 인바운드 파일이 처리된 후, 즉 인바운드 파일이 Audience Manager에 [공급되고](../../faq/faq-inbound-data-ingestion.md) 트레이트 자격 검증이 발생할 때 발생합니다.
* **고유한 특성: 주어진 시간 범위에서 프로필에 이 트레이트를 추가한 고유한 사용자의 수입니다.**
* **총 특성 수: 이 트레이트에 대해 현재 자격 조건을 갖춘 고유한 사용자 수입니다.**

   ![Trait-Graph](assets/trait-summary.png)

* **ID 유형 분류**: 처음 세 개 항목에는 가장 높은 인구 카운트가 포함된 상위 3 개 장치 간 데이터 소스가 내림차순으로 표시됩니다. 네 번째 항목에는 맨 위 3에 속하지 않은 장치 간 데이터 소스에서 특성에 대해 자격을 부여한 다른 [!DNL DPUUIDs] 모든 ([!DNL CRM IDs]) 의 합계가 표시됩니다. 이 보고서는 페이지 오른쪽 상단의 [!UICONTROL Show Results By] 드롭다운 메뉴에서 장치 간 ID를 선택하는 경우에만 나타납니다. 기본 드롭다운 옵션은 이 보고서가 표시되지 않는 곳입니다 [!UICONTROL Device ID].

   ![Trait-Graph](assets/trait-identity.png)


## 특성 표현식 {#trait-expression}

[!UICONTROL Trait Expression] 이 섹션에서는 사용자가 트레이트를 사용할 수 있도록 충족해야 하는 기준을 보여 줍니다. 이러한 규칙은 트레이트를 만들거나 [편집할 때 설정됩니다](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## 특성 세그먼트 {#trait-segments}

[!UICONTROL Segments with this Trait] 섹션에는 선택한 속성이 속하는 모든 세그먼트가 나열됩니다. 세그먼트 이름을 클릭하여 해당 세그먼트에 대한 세부 사항을 볼 수 있습니다.

![](assets/traitSegments.png)

## 특성 감사/기록 로그 {#trait-audit-history}

규칙 기반 트레이트와 온보딩 트레이트에 대해, 트레이트 [!UICONTROL Trait Expression Change History] 표현식 규칙에 대한 마지막 10 개 변경 사항과 이러한 규칙을 만든 사람을 보여줍니다. 트레이트에 10 개가 넘는 변경 사항이 있는 경우를 클릭하여 **[!UICONTROL Export to CSV]** 전체 감사 로그를 다운로드합니다. 감사 로그는 폴더 또는 알고리즘 특성에 사용할 수 없습니다.

>[!NOTE]
>
>[!UICONTROL Not Available][!UICONTROL By User] 열에 해당 사용자에 대한 계정이 삭제되었음을 의미합니다.

![](assets/traitHistory.png)