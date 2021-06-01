---
description: Audience Manager 세그먼트의 구성 요소, 대상 자격 기준을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.
landing-page-description: 세그먼트의 구성 요소, 대상 자격 기준을 설정하는 데 사용되는 표현식 및 데이터가 전송되는 방법을 설명합니다.
seo-title: 신호, 트레이트 및 세그먼트
solution: Audience Manager
title: 신호, 트레이트 및 세그먼트
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 참조
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---

# [!UICONTROL Signals],  [!UICONTROL Traits]및  [!UICONTROL Segments] {#signals-traits-and-segments}

[!DNL Audience Manager] [!UICONTROL segment] 의 구성 요소, 대상 자격 기준을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.

## 조성물 및 목적

[!DNL Audience Manager] 데이터는  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments]및 관련 자격 규칙으로 구성됩니다. 데이터 요소와 규칙이 결합하여 [!UICONTROL segments] 만들기. [!UICONTROL Segments] 사이트 방문자를 관련 그룹으로 구성합니다. 다음 표에서는 [!DNL Audience Manager] [!UICONTROL segment]에 있는 세 개의 주요 구성 요소를 정의합니다.

| 요소 | 다음으로 구성됨 | 예 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 는 에서 가장 작은 데이터  [!DNL Audience Manager] 단위이며  [키-값 쌍으로 표현됩니다](../reference/key-value-pairs-explained.md).<br><br><ul><li>키는 데이터 세트(예: 성별, 색상, 가격)를 정의하는 상수입니다.</li><li>값은 상수(예: 남성/여성, 녹색, 100)와 관련된 변수입니다.</li></ul>비교 연산자는 키-값 쌍에 참여하고 해당 쌍 간의 관계를 설정합니다. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 하나 이상의 [!UICONTROL signals].<br><br> 조합 [!DNL Boolean] 표현식 및 비교 연산자를 사용하여  [!UICONTROL trait] 자격 규칙을 만들 수 있습니다. <br><br> [!UICONTROL traits] 및  [!UICONTROL trait] 그룹 조합을 사용하여 정확한 자격 요구 사항을 생성합니다. | 사용 가능한 [!UICONTROL signals]에서 다음과 같이 표시되는 `High End Camera Browser` 규칙을 만들 수 있습니다.`product=camera AND price>1000` |
| [!UICONTROL Segment] | 공통 속성 세트를 공유하고 관련 [!UICONTROL traits]에 대한 자격이 있는 사용자입니다. [!DNL Boolean] 표현식과 최신성/빈도 요구 사항을 함께 사용하여  [!UICONTROL segment] 자격 규칙을 만들 수 있습니다.<br><br>  [!UICONTROL trait] 및  [!UICONTROL segment] 규칙 조합을 사용하여 정확한 자격 요구 사항을 만듭니다. | 사용 가능한 [!UICONTROL traits] 및 [!UICONTROL signals]에서 [!UICONTROL segment] 규칙을 만들 수 있습니다.`(product=camera AND type=digital SLR) OR (price>1000)` |

아래 다이어그램을 사용하여 [!UICONTROL signals], [!UICONTROL traits] 및 [!UICONTROL segments] 간의 관계에 대한 mental note를 유지합니다.

![](assets/signals-traits-segments.png)

**시각적  [!UICONTROL Traits] 도구 및  [!UICONTROL Segment] 코드 편집기를 사용하여 빌드 및 규칙**

클라이언트는 [!DNL Audience Manager] 사용자 인터페이스에서 시각적 도구 및 코드 편집기로 [!UICONTROL traits] 및 [!UICONTROL segments]을 관리합니다. 시각적 도구를 사용하여 검색 기능, 팝업 옵션, 드롭다운 메뉴 및 끌어서 놓기 기능을 사용하여 규칙을 만들 수 있습니다. 코드 편집기는 고급 사용자에게 대상 세그멘테이션 기준을 프로그래밍 방식으로 개발하는 방법을 제공합니다.

**데이터 전송 대상 이벤트 호출[!DNL Audience Manager]**

이벤트 호출은 웹 사이트에서 [!DNL Audience Manager](으)로 데이터를 보냅니다. 이 호출에는 [!DNL HTTP] 요청에 [!UICONTROL signal], [!UICONTROL trait] 및 [!UICONTROL segment] 데이터가 포함됩니다. 이벤트 자체는 [!DNL URL] 문자열의 `/event` 부분 뒤에 오는 모든 것입니다. 아래 예와 같이, 이 프로세스에는 여러 변수를 [!DNL Audience Manager]에 전달하려면 단일 이벤트 호출만 필요합니다.

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [세그먼트: 목적, 구성 및 규칙](../features/segments/segments-purpose.md)

