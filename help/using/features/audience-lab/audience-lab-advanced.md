---
description: 이 문서에서는 Audience Lab 중복 할당 템플릿과 세그먼트 거부 기능을 위한 고급 기능을 제공하는 두 가지 기능에 대해 설명합니다.
seo-description: 이 문서에서는 Audience Lab 중복 할당 템플릿과 세그먼트 거부 기능을 위한 고급 기능을 제공하는 두 가지 기능에 대해 설명합니다.
seo-title: Audience Lab 고급 기능
solution: Audience Manager
title: Audience Lab 고급 기능
uuid: 0 f 57 d 634-caa 0-40 da -81 a 2-c 23 fbd 299 bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] 고급 기능 {#audience-lab-advanced-functionality}

This article describes two features which provide advanced functionality for [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] and [!DNL Segment Holdout].

## Duplicate Allocation Template {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], the [!DNL Allocation Template] represents the various selections you make when creating a test group:

* 테스트 세그먼트 사이에 장치 배포;
* 테스트 세그먼트를 대상에 매핑하는 경우;
* 테스트 그룹에 사용하는 전환 특성;
* 테스트 그룹이 선택한 대상에 게시하는 날짜 범위입니다.

할당 템플릿을 복제하면 다른 기본 세그먼트에 대해 테스트 세그먼트 및 대상의 동일한 배포를 새 테스트 그룹에 재사용할 수 있습니다. 할당 템플릿의 예가 아래에 나와 있습니다. The image is taken from the [!UICONTROL Summary & Finalize] step in the **Create Test Group** workflow.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 중복 할당 템플릿 사용

Create an initial test group, then select **[!UICONTROL Duplicate Allocation Template]** to reuse the same settings across multiple test groups. 예를 들어, 여러 세그먼트에 대한 여러 대상의 유효성을 결정할 테스트를 실행하는 경우 이 기능을 사용할 수 있습니다.

1. Audience Lab 기본 보기에서 새 테스트 그룹으로 재현할 할당 템플릿을 소유한 테스트 그룹을 검색합니다. In the drop-down box, select **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. In the [!UICONTROL Create Test Group] wizard, you can specify a base segment and rename your test segments, if you wish.
3. *다음을* 수정할 수 없습니다.

   * 테스트 세그먼트 사이에 장치 배포;
   * 전환 특성;
   * 대상에 테스트 세그먼트 매핑. 매핑 키만 필요한 대상에 대해서만 채울 수 있습니다.
   * 테스트 그룹이 선택한 대상에 게시할 날짜 범위입니다.

4. Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.

## Test Segment Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] 는 고객 요청에 대해 활성화된 고급 기능입니다. Please contact [!DNL Customer Care] or [!DNL Adobe Consulting] to activate this feature.

이 기능을 사용하여 대상의 일부를 테스트에 포함되지 않도록 합니다. 선택한 백분율은 테스트 밖으로 제외됩니다. 이렇게 하면 타깃팅된 (대상에 활성화된) 대상이나 타깃팅되지 않은 (홀드 그룹) 대상에서 전환 수를 측정하고 비교할 수 있습니다.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Test Segment Holdout 사용

1. Create a new test group by using the [!UICONTROL Create Test Group] wizard.
1. **[!UICONTROL Allocate Test Segment]** 단계에서, 테스트 대상에서 제외할 대상 부분을 선택할 수 있습니다.

   ![목록 항목](assets/test-segment-holdout.png)

1. 슬라이더를 사용하여 테스트로부터 유지할 장치 수를 조정합니다. 테스트 세그먼트 1와 테스트 세그먼트 2가 이제 전체 장치의 70%만 차지하는지 확인합니다.

   ![](assets/test-segment-holdout-selected.png)

1. **[!UICONTROL Create Test Group]** 워크플로우의 나머지 단계를 살펴보고 선택 사항에 만족스러우면 선택합니다 **[!UICONTROL Finalize Group]** . 이제 테스트 그룹에서 테스트 대상이 되는 테스트 그룹이 있습니다.
