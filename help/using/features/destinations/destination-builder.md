---
description: 대상 빌더를 사용하면 쿠키 기반 또는 DNL URL 대상을 만들 수 있습니다. 대상 빌더로 서버 간(S2S) 대상을 만들 수는 없지만, 해당 세그먼트 매핑을 관리할 수는 있습니다. S2S 대상을 설정하려면 컨설턴트에게 문의하십시오. 대상 빌더는 대상 데이터 > 대상에 있습니다.
seo-description: 대상 빌더를 사용하면 쿠키 기반 또는 DNL URL 대상을 만들 수 있습니다. 대상 빌더로 서버 간(S2S) 대상을 만들 수는 없지만, 해당 세그먼트 매핑을 관리할 수는 있습니다. S2S 대상을 설정하려면 컨설턴트에게 문의하십시오. 대상 빌더는 대상 데이터 > 대상에 있습니다.
seo-title: 대상 빌더
solution: Audience Manager
title: 대상 빌더
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# 대상 빌더 {#destination-builder}

[!UICONTROL Destination Builder] 쿠키 기반 또는  [!DNL URL] 대상을 만들 수 있습니다. 서버 간([!DNL S2S]) 대상([!UICONTROL Destination Builder])은 만들 수 없지만 해당 세그먼트 매핑을 관리할 수 있습니다. 컨설턴트에 문의하여 [!DNL S2S] 대상을 설정하십시오. [!UICONTROL Destination Builder] 에 있습니다 **[!UICONTROL Audience Data > Destinations]**.

## 대상 빌더 설정 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 다음 섹션 및 설정으로 구성됩니다.

| [!UICONTROL Destination Builder] 섹션 | 용도 |
|--- |--- |
| 기본 정보 | 대상 이름을 지정하고, 설명하고, 대상 유형([!DNL URL] 또는 [!DNL cookie]) 및 플랫폼(모두, [!DNL Android], 브라우저 또는 [!DNL iOS])을 선택하는 데 사용됩니다. |
| 구성 | 다음을 위한 컨트롤이 포함되어 있습니다.<br/><ul><li>키-값 데이터를 [!DNL URL] 대상에 전달합니다. 데이터를 개별 키-값 쌍이나 직렬화된 키-값 쌍으로 보낼 수 있습니다. 자세한 내용은 [대상 직렬화](../../features/destinations/key-value-pairs.md#destination-serialized) 및 [표준 및 직렬 키-값 쌍](../../features/destinations/key-value-pairs.md)을 참조하십시오. </li><li>쿠키 이름, 도메인, 크기, 만료 간격, 데이터 형식 등과 같은 쿠키 대상의 요소</li></ul> |
| 세그먼트 매핑 | 보고서에: <br/><ul><li>모든 대상 유형과 연관된 세그먼트를 검색, 추가 및 관리합니다. </li><li>개별 세그먼트에서 배달 우선 순위를 설정합니다([!DNL cookie] 기반 세그먼트만).</li></ul> |

## 데이터 배달 방법 {#data-delivery-methods}

브라우저 [!DNL cookie]에 쓰거나 오프라인 서버 간 데이터 전송을 통해 정보를 [!DNL URL] 문자열을 통해 전달하여 대상에 보냅니다.

* [!DNL URL] 사용자가 페이지에서 작업을 수행할 때 쿠키 기반 대상이 동기식으로 데이터를 전송합니다.
* 서버 간 데이터 전송은 비동기 방식이며 사용자가 페이지를 떠난 후에도 오래 발생할 수 있습니다. 선택하는 전달 유형은 비즈니스 요구 사항과 특정 데이터 파트너가 데이터를 수신하고자 하거나 받을 수 있는 방법에 따라 달라집니다.

자세한 내용은 [대상 유형 선택 방법](../../features/destinations/destinations.md)을 참조하십시오.