---
description: 세그먼트의 구성 요소와 대상자 자격 기준을 설정하는 데 사용되는 표현식에 대해 알아봅니다. 또한 데이터가 전송되는 방식에 대한 정보를 살펴보십시오.
landing-page-description: 세그먼트의 구성 요소와 대상자 자격 기준을 설정하는 데 사용되는 표현식에 대해 알아봅니다. 또한 데이터가 전송되는 방식에 대한 정보를 살펴보십시오.
short-description: Learn about the components of a segment and the expressions used to set audience qualification criteria. Also find information about how data is transmitted.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: 신호, 트레이트 및 세그먼트
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL Signals], [!UICONTROL Traits], 및 [!UICONTROL Segments] {#signals-traits-and-segments}

의 구성 요소에 대해 설명합니다 [!DNL Audience Manager] [!UICONTROL segment], 대상 자격 기준을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.

## 조성물 및 목적

[!DNL Audience Manager] 데이터는 다음과 같이 구성됩니다 [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments], 및 관련 자격 규칙 을 참조하십시오. 데이터 요소와 규칙이 결합하여 만들기 [!UICONTROL segments]. [!UICONTROL Segments] 사이트 방문자를 관련 그룹으로 구성합니다. 다음 표에서는 [!DNL Audience Manager] [!UICONTROL segment].

| 요소 | 다음으로 구성됨 | 예 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 에서 가장 작은 데이터 단위입니다. [!DNL Audience Manager] 및에 [키 값 쌍](../reference/key-value-pairs-explained.md).<br><br><ul><li>키는 데이터 세트(예: 성별, 색상, 가격)를 정의하는 상수입니다.</li><li>값은 상수(예: 남성/여성, 녹색, 100)와 관련된 변수입니다.</li></ul>비교 연산자는 키-값 쌍에 참여하고 해당 쌍 간의 관계를 설정합니다. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 하나 이상의 조합 [!UICONTROL signals].<br><br> [!DNL Boolean] 표현식 및 비교 연산자를 사용하여 [!UICONTROL trait] 자격 규칙. <br><br>조합으로 정확한 자격 요구 사항 만들기 [!UICONTROL traits] 및 [!UICONTROL trait] 그룹 을 참조하십시오. | 사용 가능한 [!UICONTROL signals]를 만들 수 있습니다 `High End Camera Browser` 다음으로 표시되는 규칙: `product=camera AND price>1000` |
| [!UICONTROL Segment] | 공통 속성 세트를 공유하고 관련 자격이 있는 사용자 [!UICONTROL traits]. [!DNL Boolean] 최신성/빈도 요구 사항과 함께 표현식을 사용하여 [!UICONTROL segment] 자격 규칙.<br><br> 조합으로 정확한 자격 요구 사항 만들기 [!UICONTROL trait] 및 [!UICONTROL segment] 규칙. | 사용 가능한 [!UICONTROL traits] 및 [!UICONTROL signals]를 만들 수 있습니다 [!UICONTROL segment] 다음으로 표시되는 규칙:`(product=camera AND type=digital SLR) OR (price>1000)` |

아래 다이어그램을 사용하여 다음 사이의 관계에 대한 mental note를 유지합니다 [!UICONTROL signals], [!UICONTROL traits], 및 [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**빌드 [!UICONTROL Traits] 및 [!UICONTROL Segment] 시각적 도구 및 코드 편집기를 사용한 규칙**

클라이언트 관리 [!UICONTROL traits] 및 [!UICONTROL segments] 에서 시각적 도구 및 코드 편집기 사용 [!DNL Audience Manager] 사용자 인터페이스. 시각적 도구를 사용하여 검색 기능, 팝업 옵션, 드롭다운 메뉴 및 끌어서 놓기 기능을 사용하여 규칙을 만들 수 있습니다. 코드 편집기는 고급 사용자에게 대상 세그멘테이션 기준을 프로그래밍 방식으로 개발하는 방법을 제공합니다.

**데이터 전송 대상 이벤트 호출[!DNL Audience Manager]**

이벤트 호출은 웹 사이트에서 로 데이터를 전송합니다 [!DNL Audience Manager]. 이 호출에는 다음이 포함됩니다 [!UICONTROL signal], [!UICONTROL trait], 및 [!UICONTROL segment] 의 데이터 [!DNL HTTP] 요청. 이벤트 자체는 `/event` 일부 [!DNL URL] 문자열. 아래 예와 같이, 이 프로세스에는 여러 변수를 전달하려면 단일 이벤트 호출만 필요합니다 [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [세그먼트: 목적, 구성 및 규칙](../features/segments/segments-purpose.md)

