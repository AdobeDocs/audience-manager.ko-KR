---
description: 단순 픽셀(트레이트 자격을 평가하는 데 사용할 수 있음)은 실시간 데이터 전송을 수행합니다. Audience Manager 인터페이스를 사용하면 클라이언트는 셀프 서비스 기반으로 픽셀 수를 만들 수 있습니다. 픽셀 문자열은 간단한 ID 또는 키-값 쌍으로 구성됩니다.
seo-description: 단순 픽셀(트레이트 자격을 평가하는 데 사용할 수 있음)은 실시간 데이터 전송을 수행합니다. Audience Manager 인터페이스를 사용하면 클라이언트는 셀프 서비스 기반으로 픽셀 수를 만들 수 있습니다. 픽셀 문자열은 간단한 ID 또는 키-값 쌍으로 구성됩니다.
seo-title: 픽셀 기반 데이터 전송
solution: Audience Manager
title: 픽셀 기반 데이터 전송
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 4%

---


# 픽셀 기반 데이터 전송 {#pixel-based-data-transfers}

단순 픽셀(트레이트 자격을 평가하는 데 사용할 수 있음)은 실시간 데이터 전송을 수행합니다. Audience Manager 인터페이스를 사용하면 클라이언트는 셀프 서비스 기반으로 픽셀 수를 만들 수 있습니다. 픽셀 문자열은 간단한 ID 또는 키-값 쌍으로 구성됩니다.

<!-- c_rt_inbound_pixel_transfers.xml -->

인바운드 데이터 전송을 활성화하려면 공급업체 및 클라이언트는 다음을 수행합니다.

1. 공급업체 또는 파트너가 실행할 트레이트를 결정합니다.
1. 트레이트 픽셀을 가져옵니다. 트레이트 목록 화면에서 **[!UICONTROL Actions]** 열 위로 마우스를 가져간 다음 원하는 트레이트에 대해 **[!UICONTROL Get trait URL]** 기호를 클릭합니다.
1. 공급업체 또는 파트너에 [!DNL URL]을(를) 제공하십시오.

## 예

이 기본 이벤트 호출은 특성 ID 1234를 [!DNL Audience Manager]으로 보냅니다.

```
https://something.demdex.net/event?d_sid=1234
```

이벤트 호출에서 특성 ID를 직렬화하여 페이지에서 `HTTP` 트래픽을 줄일 수 있습니다. 다음 예와 같이 URL 문자열에 추가 트레이트 ID를 추가합니다.

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
