---
description: 만들기 및 업데이트 워크시트는 단일 작업에서 여러 규칙을 적용할 수 있는 traitRule 헤더를 허용합니다. 다음 지침에 따라 벌크 규칙 요청을 수행합니다.
seo-description: 만들기 및 업데이트 워크시트는 단일 작업에서 여러 규칙을 적용할 수 있는 traitRule 헤더를 허용합니다. 다음 지침에 따라 벌크 규칙 요청을 수행합니다.
seo-title: 트레이트 규칙 및 세그먼트 규칙 만들기 또는 업데이트
solution: Audience Manager
title: 트레이트 규칙 및 세그먼트 규칙 만들기 또는 업데이트
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 10%

---

# 트레이트 규칙 및 세그먼트 규칙 만들기 또는 업데이트{#create-or-update-trait-rules-and-segment-rules}

만들기 및 업데이트 워크시트는 단일 작업에서 여러 규칙을 적용할 수 있는 traitRule 헤더를 허용합니다. 다음 지침에 따라 벌크 규칙 요청을 수행합니다.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC 그룹 ](../../features/administration/administration-overview.md) 권한 [!DNL Audience Manager] 이 UI에 할당되어  [!UICONTROL Bulk Management Tools]있습니다.

## 트레이트 규칙 작업 {#trait-rules}

워크시트에서 트레이트 규칙 열은 부울 표현식, 비교 연산자 및 정규 표현식으로 구성된 규칙을 반환하고 허용합니다. [!DNL Audience Manager]에서 트레이트 또는 세그먼트 빌더로 규칙을 만들어 워크시트에 복사할 수 있습니다. 또는 규칙 구문을 잘 알고 있는 경우 워크시트에 직접 표현식을 쓸 수 있습니다.

## 규칙 빌더 예 {#rule-builder-example}

예를 들어 [!UICONTROL Segment Builder] 을 사용하여 벌크 워크시트에 추가할 수 있는 규칙을 만드는 방법을 보여 주는 예제를 살펴보겠습니다. 그러나 이러한 도구에 대한 단계별 지침은 아닙니다. 대신 이미 만들어진 간단한 규칙으로 시작합니다. 규칙 빌더를 사용하는 방법에 대한 지침은 [세그먼트 빌더](../../features/segments/segment-builder.md) 및 [트레이트 빌더](../../features/traits/about-trait-builder.md)를 참조하십시오.

시각적 규칙 빌더를 사용하여 3개의 트레이트와 부울 [!UICONTROL AND] 연산자로 세그먼트 규칙을 만들었습니다.

![](assets/visualrule.png)

**[!UICONTROL Code View]** 을 클릭하여 이 규칙의 텍스트 버전을 가져옵니다.

>[!TIP]
>
>**[!UICONTROL Validate Expression]** 을 클릭하여 규칙 논리를 확인합니다. 이렇게 하면 잘못된 규칙을 업로드하지 못하는 데 도움이 됩니다.

![](assets/coderule.png)

규칙을 [!UICONTROL Bulk Management Tools] 워크시트에 붙여 넣고 변경 사항을 커밋하여 세그먼트 규칙을 일괄적으로 업데이트합니다.

![](assets/segmentrule.png)

## 고유한 규칙 만들기 {#create-rules}

[!UICONTROL Rule Builder] 외부에 자신만의 규칙을 작성할 수 있습니다. 시작하기 전에 연산자, 표현식 및 필수 변수와 같은 사항을 다루는 설명서를 읽어 보십시오. 다음 사항을 검토하는 것이 좋습니다.

* [트레이트 빌더에서 비교 연산자 사용](../../features/traits/trait-comparison-operators.md)
* [작업 순서](../../features/traits/trait-operator-precedence.md)
* [주요 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)
* [부울 및 비교 연산자가 있는 샘플 표현식](../../features/traits/trait-expression-samples.md)
