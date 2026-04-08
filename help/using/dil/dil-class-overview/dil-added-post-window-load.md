---
description: 창이 로드된 후 DIL에 로드되었음을 알리는 데 사용됩니다.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
TQID: https://experienceleague.adobe.com/gLycCnA5nwb-91miUts-VvlFK4YfVxvju7GAl-NZW8w
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: b82b475d-1e7d-46c6-9172-1f9c73004b11
subfeature_v2: id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 98
ht-degree: 2%

---

# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>2023년 7월부터 Adobe은 [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장 개발을 중단했습니다.
>
>기존 고객은 [!DNL DIL] 구현을 계속 사용할 수 있습니다. 그러나 Adobe은 이 시점 이후에는 [!DNL DIL]을(를) 개발하지 않습니다. 고객은 장기 데이터 수집 전략에 대해 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)을(를) 평가하는 것이 좋습니다.
>
>2023년 7월 이후에 새로운 데이터 수집 통합을 구현하려는 고객은 대신 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)을 사용해야 합니다.

창이 로드된 후 DIL에 로드되었음을 알리는 데 사용됩니다.

**함수 서명:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## 샘플 코드

```
DIL.isAddedPostWindowLoad();
```
