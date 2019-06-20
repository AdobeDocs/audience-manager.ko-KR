---
description: 단순 픽셀 (트레이트 사용자를 평가하는 데 사용 가능) 는 실시간 데이터 전송을 수행합니다. 클라이언트는 Audience Manager 인터페이스를 사용하여 셀프 서비스 기반으로 여러 픽셀을 만들 수 있습니다. 픽셀 문자열은 단순 ID 또는 키-값 쌍으로 구성됩니다.
seo-description: 단순 픽셀 (트레이트 사용자를 평가하는 데 사용 가능) 는 실시간 데이터 전송을 수행합니다. 클라이언트는 Audience Manager 인터페이스를 사용하여 셀프 서비스 기반으로 여러 픽셀을 만들 수 있습니다. 픽셀 문자열은 단순 ID 또는 키-값 쌍으로 구성됩니다.
seo-title: 픽셀 기반의 데이터 전송
solution: Audience Manager
title: 픽셀 기반의 데이터 전송
uuid: 8773 bfc 0-6 b 8 d -4 a 6 a-a 8 b 7-e 043744486 ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixel-based Data Transfers {#pixel-based-data-transfers}

단순 픽셀 (트레이트 사용자를 평가하는 데 사용 가능) 는 실시간 데이터 전송을 수행합니다. 클라이언트는 Audience Manager 인터페이스를 사용하여 셀프 서비스 기반으로 여러 픽셀을 만들 수 있습니다. 픽셀 문자열은 단순 ID 또는 키-값 쌍으로 구성됩니다.

<!-- c_rt_inbound_pixel_transfers.xml -->

인바운드 데이터 전송을 활성화하려면 공급업체 및 클라이언트가 다음을 수행합니다.

1. 공급업체 또는 파트너가 실행할 트레이트를 결정합니다.
1. 특성 픽셀을 가져옵니다. In the traits list screen, hover over the **[!UICONTROL Actions]** column and click the **[!UICONTROL Get trait URL]** symbol for the desired trait.
1. Provide the [!DNL URL] to the vendor or partner.

## 예

This basic event call sends trait ID 1234 to [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

You can serialize trait IDs in an event call to help reduce `HTTP` traffic from the page. 다음 예와 같이 URL 문자열에 추가 특성 ID를 추가합니다.

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
