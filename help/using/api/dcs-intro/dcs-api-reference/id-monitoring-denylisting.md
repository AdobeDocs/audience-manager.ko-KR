---
description: DCS는 수신하는 ID를 모니터링하고 짧은 시간에 비정상적으로 높은 비율로 전송되는 ID를 차단 목록에 추가합니다.
keywords: id;모니터링;dcs
seo-description: DCS는 수신하는 ID를 모니터링하고 짧은 시간에 비정상적으로 높은 비율로 전송되는 ID를 차단 목록에 추가합니다.
seo-title: ID 모니터링 및 차단 목록에 추가
solution: Audience Manager
title: ID 모니터링 및 차단 목록에 추가
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# ID 모니터링 및 차단 목록에 추가

[!DNL DCS] 은 수신하는 ID를 모니터링하고 짧은 시간에 비정상적으로 높은 비율로 전송되는 ID를 차단 목록에 추가합니다.

## 개요

악성 활동으로부터 Audience Manager 인프라를 보호하기 위해 [!DNL DCS]은(는) 고급 알고리즘을 사용하여 수신한 ID를 모니터링합니다. 이는 [!UICONTROL Data Provider Unique User ID]s([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s) 또는 [!UICONTROL Experience Cloud ID]s([!UICONTROL ECID]s)일 수 있습니다. Audience Manager에서 지원하는 ID에 대한 자세한 내용은 Audience Manager](../../../reference/ids-in-aam.md)의 [ID 색인 을 참조하십시오.

[!DNL DCS] 은 이러한 ID를 수신하는 빈도를 모니터링하여 잠재적인 악의적인 활동을 감지합니다. [!DNL DCS]에서 짧은 시간 내에 주어진 ID에 대한 비정상적으로 많은 [!DNL DCS] 요청을 감지하면 해당 ID가 차단 목록에 추가됩니다.

## 오류 코드

[!DNL DCS]에서 받은 오류 코드로 차단 목록에 추가된 ID를 식별할 수 있습니다. 받을 수 있는 오류 코드는 다음과 같습니다.

* 303:차단된 고객 ID;
* 306:차단된 선언된 장치 ID;
* 307:ID에 대한 프로필 작업이 차단되었습니다.

받을 수 있는 오류 코드에 대한 자세한 내용은 [DCS 오류 코드, 메시지 및 예제](dcs-error-codes.md)를 참조하십시오.

## 차단 목록에서 ID 제거

차단 목록에 추가된 ID는 잘못된 데이터 보고로 연결되므로 향후 요청에서 사용해서는 안 됩니다. [!DNL DCS]은 차단 목록에서 ID 제거를 지원하지 않습니다.

## ID 동기화에 미치는 영향

[!DNL DCS] 호출에는 하나 이상의 ID 유형이 포함될 수 있습니다. 해당 ID가 차단 목록에 추가되는 경우 단일 ID가 포함된 호출은 완전히 무시되며 ID 동기화는 발생하지 않습니다.

여러 ID 호출에 차단 목록에 추가된 ID도 포함되어 있으면 [!DNL DCS]은 거부된 ID를 무시하고 동기화에 나머지 허용된 ID만 사용합니다.

## ID 차단 목록에 추가 원인 및 수정 사항

차단 목록에 ID가 추가되는 가장 빈번한 원인은 고객 인프라와 Audience Manager 간의 잘못된 통합입니다. 차단 목록에 추가된 ID를 식별할 때 Audience Manager 통합을 철저하게 검토하십시오. 다른 Experience Cloud 솔루션 또는 외부 시스템과 작동하도록 Audience Manager을 구성하는 방법에 대한 자세한 내용은 **구현 및 통합 안내서** 를 참조하십시오.

차단 목록에 ID가 추가되는 또 다른 빈번한 원인은 색인 보트(웹 크롤러)이며 일반적으로 트래픽이 증가하여 동일한 ID가 [!DNL DCS]로 여러 번 전송되는 것입니다. 차단 목록에 ID가 추가되는 이유로 인덱싱 보트를 식별하는 경우 웹 사이트에 대한 보트 액세스를 제한해야 합니다.

통합 문제를 식별하기 어려운 경우 고객 지원 센터에 문의하는 것을 주저하지 마십시오. 지원 요청을 열기 전에 브라우저의 `.har` `HTTP` 아카이브를 준비했는지 확인합니다. 이 아카이브는 지원 팀이 ID가 차단 목록에 추가된 이유를 식별하는 데 도움이 됩니다.
