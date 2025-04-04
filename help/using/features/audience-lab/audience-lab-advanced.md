---
description: 이 문서에서는 대상 랩 중복 할당 템플릿 및 세그먼트 홀드아웃에 대한 고급 기능을 제공하는 두 가지 기능에 대해 설명합니다.
seo-description: This article describes two features which provide advanced functionality for Audience Lab  Duplicate Allocation Template and Segment Holdout.
seo-title: Audience Lab Advanced Functionality
solution: Audience Manager
title: 대상 랩 고급 기능
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---

# [!DNL Audience Lab] 고급 기능 {#audience-lab-advanced-functionality}

이 문서에서는 [!DNL Audience Lab]에 고급 기능을 제공하는 두 가지 기능에 대해 설명합니다. [!DNL Duplicate Allocation Template] 및 [!DNL Segment Holdout].

## 중복 할당 템플릿 {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

[!DNL Audience Lab]에서 [!DNL Allocation Template]은(는) 테스트 그룹을 만들 때 선택하는 다양한 항목을 나타냅니다.

* 테스트 세그먼트 간 장치 분포
* 대상에 대한 테스트 세그먼트 매핑
* 테스트 그룹에 사용하는 전환 트레이트
* 테스트 그룹이 선택한 대상에 게시하는 날짜 범위입니다.

할당 템플릿을 복제하면 새 테스트 그룹에서 다른 기본 세그먼트에 대해 동일한 테스트 세그먼트 및 대상 배포를 재사용할 수 있습니다. 할당 템플릿의 예가 아래에 나와 있습니다. 이미지는 **테스트 그룹 만들기** 워크플로의 [!UICONTROL Summary & Finalize] 단계에서 가져온 것입니다.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 중복 할당 템플릿 사용

초기 테스트 그룹을 만든 다음 **[!UICONTROL Duplicate Allocation Template]**&#x200B;을(를) 선택하여 여러 테스트 그룹에서 동일한 설정을 다시 사용합니다. 예를 들어, 여러 세그먼트에 대한 여러 대상의 효과를 확인하려는 테스트를 실행하는 경우 이 기능을 사용할 수 있습니다.

1. 대상 랩 기본 보기에서 새 테스트 그룹에서 할당 템플릿을 재현할 테스트 그룹을 검색합니다. 드롭다운 상자에서 **[!UICONTROL Duplicate Allocation Template]**&#x200B;을(를) 선택합니다.

   ![](assets/duplicate-allocation-template.png)

2. [!UICONTROL Create Test Group] 마법사에서 기본 세그먼트를 지정하고 원하는 경우 테스트 세그먼트의 이름을 변경할 수 있습니다.
3. *수정할 수 없음*:

   * 테스트 세그먼트 간 장치 분포
   * 전환 트레이트;
   * 대상에 대한 테스트 세그먼트 매핑입니다. 매핑 키가 필요한 대상에 대해서만 매핑 키를 입력할 수 있습니다.
   * 테스트 그룹이 선택한 대상에 게시할 날짜 범위입니다.

4. 이전 단계에서 추가한 정보를 검토하고 **[!UICONTROL Finalize Group]**&#x200B;을(를) 선택합니다.

## 테스트 세그먼트 유지 {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout]은(는) 고객 요청에 따라 활성화된 고급 기능입니다. 이 기능을 활성화하려면 [!DNL Customer Care] 또는 [!DNL Adobe Consulting]에 문의하십시오.

이 기능을 사용하여 대상의 일부가 테스트에 포함되지 않도록 할 수 있습니다. 선택한 백분율이 테스트에서 제외됩니다. 이 방법을 통해 타깃팅된(대상에서 활성화됨) 및 타깃팅되지 않은(홀드아웃 그룹) 대상의 전환 수를 측정하고 비교할 수 있습니다.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 테스트 세그먼트 홀드아웃 사용

1. [!UICONTROL Create Test Group] 마법사를 사용하여 새 테스트 그룹을 만듭니다.
1. **[!UICONTROL Allocate Test Segment]** 단계에서는 테스트 대상에서 제외할 대상의 일부를 선택할 수 있습니다.

   ![목록 항목](assets/test-segment-holdout.png)

1. 슬라이더를 사용하여 테스트에서 제외할 장치 수를 조정합니다. 이제 테스트 세그먼트 1 및 테스트 세그먼트 2가 전체 장치의 70%만 구성하는 방법에 주목하십시오.

   ![](assets/test-segment-holdout-selected.png)

1. **[!UICONTROL Create Test Group]** 워크플로의 나머지 단계를 거치고 선택에 만족하면 **[!UICONTROL Finalize Group]**&#x200B;을(를) 선택하십시오. 이제 대상의 일부가 테스트 대상에서 제외된 테스트 그룹이 있습니다.
