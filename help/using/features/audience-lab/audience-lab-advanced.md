---
description: 이 문서에서는 Audience Lab 중복 할당 템플릿 및 세그먼트 홀드에 고급 기능을 제공하는 두 가지 기능에 대해 설명합니다.
seo-description: 이 문서에서는 Audience Lab 중복 할당 템플릿 및 세그먼트 홀드에 고급 기능을 제공하는 두 가지 기능에 대해 설명합니다.
seo-title: 대상 랩 고급 기능
solution: Audience Manager
title: 대상 랩 고급 기능
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 1%

---


# [!DNL Audience Lab] 고급 기능  {#audience-lab-advanced-functionality}

이 문서에서는 [!DNL Audience Lab]에 대한 고급 기능을 제공하는 두 가지 기능에 대해 설명합니다.[!DNL Duplicate Allocation Template] 및 [!DNL Segment Holdout].

## 중복된 할당 템플릿 {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

[!DNL Audience Lab]에서 [!DNL Allocation Template]는 테스트 그룹을 만들 때 선택한 다양한 항목을 나타냅니다.

* 테스트 세그먼트 간 장치 배포;
* 대상에 테스트 세그먼트 매핑;
* 테스트 그룹에 사용하는 전환 특성;
* 테스트 그룹이 선택한 대상에 게시하는 날짜 범위입니다.

할당 템플릿을 복제하면 새 테스트 그룹에서 다른 기본 세그먼트에 대해 동일한 테스트 세그먼트와 대상 배포를 재사용할 수 있습니다. 할당 템플릿의 예는 아래에 나와 있습니다. 이미지는 **테스트 그룹 만들기** 워크플로우의 [!UICONTROL Summary & Finalize] 단계에서 가져옵니다.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### 중복 할당 템플릿 사용

초기 테스트 그룹을 만든 다음 **[!UICONTROL Duplicate Allocation Template]**&#x200B;을 선택하여 여러 테스트 그룹에서 동일한 설정을 재사용합니다. 예를 들어 여러 세그먼트에 대한 여러 대상의 효과를 판별하려는 테스트를 실행하는 경우 이 기능을 사용할 수 있습니다.

1. Audience Lab 기본 보기에서 새 테스트 그룹으로 복제할 할당 템플릿을 가진 테스트 그룹을 검색합니다. 드롭다운 상자에서 **[!UICONTROL Duplicate Allocation Template]**&#x200B;을 선택합니다.

   ![](assets/duplicate-allocation-template.png)

2. 원할 경우 [!UICONTROL Create Test Group] 마법사에서 기본 세그먼트를 지정하고 테스트 세그먼트의 이름을 변경할 수 있습니다.
3. *은(는) 수정할 수 없습니다.*:

   * 테스트 세그먼트 간 장치 배포;
   * 전환 특성;
   * 대상에 대한 테스트 세그먼트 매핑. 매핑 키만 채울 수 있습니다.
   * 테스트 그룹이 선택한 대상에 게시할 날짜 범위입니다.

4. 이전 단계에서 추가한 정보를 검토하고 **[!UICONTROL Finalize Group]**&#x200B;을 선택합니다.

## 테스트 세그먼트 홀드아웃 {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] 는 고객 요청에 따라 활성화되는 고급 기능입니다. 이 기능을 활성화하려면 [!DNL Customer Care] 또는 [!DNL Adobe Consulting]에 문의하십시오.

이 기능을 사용하여 대상 일부가 테스트에 포함되지 않도록 합니다. 선택한 백분율은 테스트에서 제외됩니다. 이렇게 하면 타깃팅된(대상에서 활성화) 및 타깃팅되지 않은(종료 그룹) 대상의 전환 수를 측정하고 비교할 수 있습니다.

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### 테스트 세그먼트 홀드아웃 사용

1. [!UICONTROL Create Test Group] 마법사를 사용하여 새 테스트 그룹을 만듭니다.
1. **[!UICONTROL Allocate Test Segment]** 단계에서 테스트에서 제외할 대상의 일부를 선택할 수 있습니다.

   ![목록 항목](assets/test-segment-holdout.png)

1. 슬라이더를 사용하여 테스트에서 제외할 장치의 수를 조정합니다. 이제 테스트 세그먼트 1과 테스트 세그먼트 2가 총 장치의 70%만을 차지하는 방법을 확인하십시오.

   ![](assets/test-segment-holdout-selected.png)

1. **[!UICONTROL Create Test Group]** 워크플로우의 나머지 단계를 거쳐 선택한 내용에 만족하면 **[!UICONTROL Finalize Group]**&#x200B;을 선택합니다. 이제 일부 청중이 테스트 대상에서 제외되는 테스트 그룹이 있습니다.
