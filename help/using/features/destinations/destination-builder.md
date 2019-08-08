---
description: 대상 빌더를 사용하여 쿠키 기반 또는 DNL URL 대상을 만들 수 있습니다. 대상 빌더에서는 서버-서버 (S 2 S) 대상을 만들 수 없지만 세그먼트 매핑을 관리할 수는 있습니다. S 2 S 대상을 설정하려면 컨설턴트에게 문의하십시오. 대상 빌더는 대상 데이터 > 대상에 있습니다.
seo-description: 대상 빌더를 사용하여 쿠키 기반 또는 DNL URL 대상을 만들 수 있습니다. 대상 빌더에서는 서버-서버 (S 2 S) 대상을 만들 수 없지만 세그먼트 매핑을 관리할 수는 있습니다. S 2 S 대상을 설정하려면 컨설턴트에게 문의하십시오. 대상 빌더는 대상 데이터 > 대상에 있습니다.
seo-title: 대상 빌더
solution: Audience Manager
title: 대상 빌더
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# 대상 빌더 {#destination-builder}

[!UICONTROL Destination Builder] 쿠키 기반 [!DNL URL] 또는 대상을 만들 수 있습니다. server-to-server ([!DNL S2S]) 대상은 만들 수는 없지만, 세그먼트 [!UICONTROL Destination Builder]매핑을 관리할 수는 있습니다. [!DNL S2S] 대상을 설정하려면 컨설턴트에게 문의하십시오. [!UICONTROL Destination Builder]**[!UICONTROL Audience Data > Destinations]**&#x200B;에 있습니다.

## 대상 빌더 설정 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 다음 섹션과 설정으로 구성됩니다.

| [!UICONTROL Destination Builder] 섹션 | 용도 |
|--- |--- |
| 기본 정보 | 대상의 이름을 지정하고, 대상을 설명하며, 대상 유형 ([!DNL URL] 또는 [!DNL cookie]) 를 선택하고 플랫폼 (모두, [!DNL Android]브라우저, 브라우저 또는 [!DNL iOS]) 를 선택하는 데 사용됩니다. |
| 구성 | 컨트롤 포함: <br/><ul><li>대상에 키-값 데이터 [!DNL URL] 전달. 데이터를 개별 또는 직렬화된 키-값 쌍으로 보낼 수 있습니다. 자세한 내용은 [대상 일련화](../../features/destinations/key-value-pairs.md#destination-serialized) 및 [표준 및 직렬 키-값 쌍을 참조하십시오](../../features/destinations/key-value-pairs.md). </li><li>쿠키 이름, 도메인, 크기, 만료 간격, 데이터 형식 등과 같은 쿠키 대상의 요소</li></ul> |
| 세그먼트 매핑 | 보고서에: <br/><ul><li>모든 대상 유형과 연관된 세그먼트를 검색, 추가 및 관리합니다. </li><li>개별 세그먼트에 대한 배달 우선 순위를 설정합니다 (-기반 세그먼트에만 [!DNL cookie]해당).</li></ul> |

## 데이터 전달 방법 {#data-delivery-methods}

[!DNL URL] 정보를 문자열을 통해 전달하거나, 브라우저에 [!DNL cookie]쓰거나, 오프라인 서버 간 데이터 전송을 통해 대상을 대상으로 전달할 수 있습니다.

* [!DNL URL] 또한 쿠키 기반의 대상은 사용자가 페이지에서 작업을 수행하면서 동기적으로 데이터를 전송합니다.
* 서버 간 데이터 전송은 비동기적이며 사용자가 페이지를 떠난 후에도 발생할 수 있습니다. 선택하는 전달 유형은 비즈니스 요구 사항과 특정 데이터 파트너가 데이터를 원하는 방법에 따라 달라집니다.

자세한 [내용은 대상 유형을](../../features/destinations/destinations.md) 선택하는 방법을 참조하십시오.