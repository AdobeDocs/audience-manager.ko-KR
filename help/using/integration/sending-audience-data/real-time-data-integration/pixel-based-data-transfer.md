---
description: 단순 픽셀(트레이트 자격을 평가하는 데 사용할 수 있음)은 실시간 데이터 전송을 수행합니다. Audience Manager 인터페이스를 사용하면 셀프 서비스 기반으로 픽셀 수를 원하는 만큼 만들 수 있습니다. 픽셀 문자열은 단순 ID 또는 키-값 쌍으로 구성됩니다.
seo-description: 단순 픽셀(트레이트 자격을 평가하는 데 사용할 수 있음)은 실시간 데이터 전송을 수행합니다. Audience Manager 인터페이스를 사용하면 셀프 서비스 기반으로 픽셀 수를 원하는 만큼 만들 수 있습니다. 픽셀 문자열은 단순 ID 또는 키-값 쌍으로 구성됩니다.
seo-title: 픽셀 기반 데이터 전송
solution: Audience Manager
title: 픽셀 기반 데이터 전송
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: 인바운드 데이터 전송
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 5%

---

# 픽셀 기반 데이터 전송 {#pixel-based-data-transfers}

단순 픽셀(트레이트 자격을 평가하는 데 사용할 수 있음)은 실시간 데이터 전송을 수행합니다. Audience Manager 인터페이스를 사용하면 셀프 서비스 기반으로 픽셀 수를 원하는 만큼 만들 수 있습니다. 픽셀 문자열은 단순 ID 또는 키-값 쌍으로 구성됩니다.

<!-- c_rt_inbound_pixel_transfers.xml -->

인바운드 데이터 전송을 활성화하려면 공급업체 및 클라이언트는 다음을 수행합니다.

1. 공급업체 또는 파트너가 실행할 트레이트를 결정합니다.
1. 트레이트의 픽셀을 가져옵니다. 트레이트 목록 화면에서 **[!UICONTROL Actions]** 열 위로 마우스를 가져가 원하는 트레이트에 대한 **[!UICONTROL Get trait URL]** 기호를 클릭합니다.
1. 공급업체 또는 파트너에게 [!DNL URL]을(를) 제공합니다.

## 예

이 기본 이벤트 호출은 트레이트 ID 1234를 [!DNL Audience Manager]으로 보냅니다.

```
https://something.demdex.net/event?d_sid=1234
```

이벤트 호출에서 트레이트 ID를 일련화하여 페이지에서 `HTTP` 트래픽을 줄일 수 있습니다. 다음 예와 같이 URL 문자열에 추가 트레이트 ID를 추가합니다.

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
