---
description: 이 보고서는 선택한 날짜 이전 30 일 동안 최소 10,000 번 실현되었고 동일한 시간 간격 동안 어느 쪽으로든 표준 편차가 1.7 보다 크거나 같은 특성 목록을 반환합니다. 이 보고서는 고유 사용자의 노출 횟수가 시간에 따라 변하는 방식을 평가하는 데 도움이 됩니다.
seo-description: 이 보고서는 선택한 날짜 이전 30 일 동안 최소 10,000 번 실현되었고 동일한 시간 간격 동안 어느 쪽으로든 표준 편차가 1.7 보다 크거나 같은 특성 목록을 반환합니다. 이 보고서는 고유 사용자의 노출 횟수가 시간에 따라 변하는 방식을 평가하는 데 도움이 됩니다.
seo-title: 일별 특성 변형 보고서
solution: Audience Manager
title: 일별 특성 변형 보고서
uuid: 4 e 82 bb 17-d 447-4 ed 1-a 4 fc-e 15 b 0 f 1 b 47 f 0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Daily Trait Variation Report {#daily-trait-variation-report}

이 보고서는 선택한 날짜 이전 30 일 동안 최소 10,000 번 실현되었고 동일한 시간 간격 동안 어느 쪽으로든 표준 편차가 1.7 보다 크거나 같은 특성 목록을 반환합니다. 이 보고서는 고유 사용자의 노출 횟수가 시간에 따라 변하는 방식을 평가하는 데 도움이 됩니다.

>[!NOTE]
>
>Audience Manager의 일별 특성 변형 보고서는 RBAC 원칙을 준수합니다. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

표준 편차는 평균 (또는 평균/예상 값) 으로부터 변화량 또는 분산의 양을 측정합니다. 표준 편차가 낮으면 데이터 포인트가 평균과 매우 유사하다는 것을 의미합니다. 표준 편차가 높으면 데이터 포인트가 넓은 값 범위에 걸쳐 분산됨을 나타냅니다.

![](assets/daily_trait_variation.png)

[!UICONTROL Date] 목록을 사용하여 보고서의 날짜를 하나 이상 선택합니다. 선택한 모든 날짜의 모든 트레이트에 대한 표준 편차 범위를 시각적으로 표시하는 색상 구분된 막대 차트가 목록 하단에 표시됩니다. 검은색 세로선은 평균을 나타냅니다.

The middle column contains a list of traits, identified by [!UICONTROL Trait ID] and [!UICONTROL Trait Name]. 트레이트를 클릭하면 다음 옵션 중에서 선택할 수 있는 팝업 대화 상자가 표시됩니다.

* **유지 관리:** 보고서에서 다른 모든 트레이트를 제거하고 이 트레이트 데이터만 표시합니다.
* **제외:** 보고서에서 이 트레이트를 제거하고 다른 모든 트레이트에 대한 데이터를 표시합니다. 여러 트레이트를 제외할 수 있습니다.
* **데이터 보기:** 해당 행에 대한 데이터를 표시할 수 있습니다. 모든 행을 텍스트 파일로 다운로드할 수도 있습니다.

[!UICONTROL Standard Deviation] 열에는 선택한 간격 동안 각 트레이트 표준 편차를 표시하는 색상 코드가 표시된 막대 차트가 표시됩니다. 빨간색 막대는 음의 표준 편차가 있는 트레이트를 나타냅니다 (데이터 포인트는 평균보다 낮음). 녹색 막대는 긍정적인 표준 편차가 있는 트레이트를 나타냅니다 (데이터 포인트는 평균 위에 있는 경향이 있습니다). 막대 위에 마우스를 놓으면 해당 트레이트를 유지하거나 제외할 수 있는 추가 정보 및 옵션이 포함된 팝업 대화 상자가 표시됩니다.

여러 형식으로 데이터를 내보내고, 보고서에 수행한 변경 사항을 되돌리거나, 자동 업데이트를 활성화하거나 비활성화하고, 보고서의 데이터를 새로 고칠 수 있도록 해주는 아이콘이 보고서 하단에 표시됩니다. See [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## 사용 사례 {#use-cases}

**예제 번호 1**: 이 보고서는 높은 계절적 수준의 트레이트가 있는 상황에서 매우 유용합니다. 예를 들어 온라인 스토어에서 다양한 유형과 가격의 계절적 프로모션을 테스트하고 있다고 가정합니다. You have the following traits defined in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Say you run the [!UICONTROL Daily Trait Variation] report on the 20th of December and you notice a solid positive deviation on the above mentioned traits in the past 30 days. 이렇게 하면 방문자가 계절 판촉 행사에 언급된 제품을 찾고 있음을 알 수 있습니다. 이러한 트렌드를 활용하려면 관심을 가지고 있는 방문자에 대한 특정 제품 카테고리에 대한 크리에이티브 크리에이티브 작업에 더 많은 노력을 투자할 수 있습니다.

**예제 2**: 이 보고서는 태그 지정 문제 또는 트레이트 잘못된 구성과 관련된 타깃팅 예외 항목을 식별하는 데 도움이 됩니다. 온라인 스토어의 카테고리를 기반으로 다음 트레이트를 정의했다고 가정해 보십시오.

* `productPage == "smartphones"`

스토어의 재구성으로 인해 브랜드 이름에 따라 스마트폰 페이지를 여러 페이지로 분할합니다. However, you forget to update the traits defined in [!DNL Audience Manager].

One month later, you run the [!UICONTROL Daily Trait Variation] report and notice a large negative deviation on the `productPage == "smartphones"` trait, although your visitor number has increased, according to your site analytics. Based on this information, you realize that you haven't updated the traits in [!DNL Audience Manager] for your new product pages, so you know that you need to create the following traits:

* productpage = = "samsung"
* productpage = = "apple"
* productpage = = "huawei"

이렇게 하면 새롭게 생성된 트레이트에 대한 대상이 자격 조건을 갖추게 됩니다.
