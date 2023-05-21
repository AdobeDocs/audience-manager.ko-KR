---
description: 대상 빌더를 사용하여 쿠키 기반 또는 DNL URL 대상을 만들 수 있습니다. 대상 빌더를 사용하여 서버 간(S2S) 대상을 만들 수는 없지만 세그먼트 매핑을 관리할 수는 있습니다. S2S 대상을 설정하려면 컨설턴트에게 문의하십시오. 대상 빌더는 대상 데이터 > 대상에 있습니다.
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: 대상 빌더
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 4%

---

# 대상 빌더 {#destination-builder}

[!UICONTROL Destination Builder] 쿠키 기반 또는 [!DNL URL] 대상. 서버 간 ( )을 만들 수 없습니다.[!DNL S2S]) 대상( [!UICONTROL Destination Builder], 하지만 세그먼트 매핑을 관리할 수 있습니다. 컨설턴트에게 연락하여 [!DNL S2S] 대상. [!UICONTROL Destination Builder] 위치: **[!UICONTROL Audience Data > Destinations]**.

## 대상 빌더 설정 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 는 다음 섹션과 설정으로 구성됩니다.

| [!UICONTROL Destination Builder] 섹션 | 용도 |
|--- |--- |
| 기본 정보 | 대상 이름을 지정하고, 설명하고, 대상 유형을 선택하는 데 사용됩니다([!DNL URL] 또는 [!DNL cookie]) 및 플랫폼(모두, [!DNL Android], 브라우저 또는 [!DNL iOS]). |
| 구성 | 다음에 대한 컨트롤을 포함합니다. <br/><ul><li>에 키-값 데이터 전달 [!DNL URL] 대상. 데이터를 개별 또는 직렬화된 키-값 쌍으로 보낼 수 있습니다. 자세한 내용은 [대상 직렬화](../../features/destinations/key-value-pairs.md#destination-serialized) 및 [표준 및 일련 키-값 쌍](../../features/destinations/key-value-pairs.md). </li><li>쿠키 이름, 도메인, 크기, 만료 간격, 데이터 형식 등과 같은 쿠키 대상의 요소</li></ul> |
| 세그먼트 매핑 | 보고서에: <br/><ul><li>모든 대상 유형과 연관된 세그먼트를 검색, 추가 및 관리합니다. </li><li>개별 세그먼트에 대한 게재 우선 순위 설정 (대상 [!DNL cookie]-기반 세그먼트만).</li></ul> |

## 데이터 전달 방법 {#data-delivery-methods}

을(를) 통해 정보를 전달하여 대상에 전송 [!DNL URL] 문자열, 브라우저에 쓰기 [!DNL cookie]또는 오프라인 서버 간 데이터 전송을 통해 수행할 수 있습니다.

* [!DNL URL] 및 쿠키 기반 대상은 사용자가 페이지에서 작업을 수행할 때 데이터를 동기적으로 전송합니다.
* 서버 간 데이터 전송은 비동기적으로 수행되며 사용자가 페이지를 떠난 후 오래 걸릴 수 있습니다. 선택하는 게재 유형은 비즈니스 요구 사항과 특정 데이터 파트너가 데이터를 받거나 받을 수 있는 방법에 따라 다릅니다.

다음을 참조하십시오 [대상 유형을 선택하는 방법](../../features/destinations/destinations.md) 추가 정보.
