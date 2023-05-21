---
description: 단순한 픽셀(사용자에게 트레이트를 부여하는 데 사용할 수 있음)은 실시간 데이터 전송을 수행합니다. Audience Manager 인터페이스를 사용하면 클라이언트가 셀프서비스 기반으로 원하는 개수의 픽셀을 만들 수 있습니다. 픽셀 문자열은 단순 ID 또는 키-값 쌍으로 구성됩니다.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: 픽셀 기반 데이터 전송
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 4%

---

# 픽셀 기반 데이터 전송 {#pixel-based-data-transfers}

단순한 픽셀(사용자에게 트레이트를 부여하는 데 사용할 수 있음)은 실시간 데이터 전송을 수행합니다. Audience Manager 인터페이스를 사용하면 클라이언트가 셀프서비스 기반으로 원하는 개수의 픽셀을 만들 수 있습니다. 픽셀 문자열은 단순 ID 또는 키-값 쌍으로 구성됩니다.

<!-- c_rt_inbound_pixel_transfers.xml -->

인바운드 데이터 전송을 활성화하기 위해 공급업체 및 클라이언트는 다음을 수행합니다.

1. 공급업체 또는 파트너가 실행할 트레이트를 결정합니다.
1. 트레이트에 대한 픽셀을 가져옵니다. 트레이트 목록 화면에서 **[!UICONTROL Actions]** 열을 클릭하고 **[!UICONTROL Get trait URL]** 원하는 트레이트에 대한 기호입니다.
1. 다음을 제공합니다 [!DNL URL] 공급업체 또는 파트너에게

## 예

이 기본 이벤트 호출은 트레이트 ID 1234를 로 보냅니다. [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

이벤트 호출에서 트레이트 ID를 직렬화하여 크기를 줄일 수 있습니다 `HTTP` 페이지의 트래픽입니다. 다음 예와 같이 URL 문자열에 추가 트레이트 ID를 추가합니다.

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
