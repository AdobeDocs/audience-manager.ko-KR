---
description: 창이 로드된 후 로드되었음을 DIL에게 알리는 데 사용됩니다.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>2023년 7월부터 Adobe은 의 개발을 중단했습니다. [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장명.
><br>
>기존 고객은 [!DNL DIL] 구현. 그러나 Adobe은 개발되지 않습니다 [!DNL DIL] 이 점을 넘어서는 것입니다. 고객은 다음을 평가하는 것이 좋습니다. [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 을 참조하십시오.
><br>
>2023년 7월 이후 새로운 데이터 수집 통합을 구현하려는 고객은 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 대신,

창이 로드된 후 로드되었음을 DIL에게 알리는 데 사용됩니다.

**함수 서명:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## 샘플 코드

```
DIL.isAddedPostWindowLoad();
```
