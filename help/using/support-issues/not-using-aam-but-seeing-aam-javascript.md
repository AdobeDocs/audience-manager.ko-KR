---
description: Audience Manager를 사용하고 있지 않지만 Javascript 디버거에 Audience Manager Javascript 호출이 있습니다. - 이유는 무엇입니까?
seo-description: Adobe는 사용하고 있지 않지만 JavaScript 디버거에 Audience Manager Javascript 호출이 포함되어 있습니다 - 이유는 무엇입니까?
seo-title: Audience Manager를 사용하고 있지 않지만 Javascript 디버거에 Audience Manager Javascript 호출이 있습니다. - 이유는 무엇입니까?
solution: Audience Manager
title: Audience Manager를 사용하고 있지 않지만 Javascript 디버거에 Audience Manager Javascript 호출이 있습니다. - 이유는 무엇입니까?
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# Adobe는 Audience Manager 고객이 아니지만 사이트에서 Audience Manager Javascript 호출을 참조하십시오.

## 질문

Adobe Audience Manager를 사용하고 있지 않지만 Javascript 디버거에서는 Audience Manager Javascript 호출이 표시됩니다.

왜 이런 일이 발생하는가?

## 답변

속성에서 Experience Cloud [Identity Service를](https://docs.adobe.com/content/help/en/id-service/using/home.html) 실행 중일 수 있습니다. 이러한 경우 Audience Manager 참조가 Audience Manager를 실행하는 속성을 참조할 필요가 없습니다. 대신 Audience Manager가 이 서비스를 구현한다는 의미입니다.

일반적으로 Audience Manager 서버 호출은 고객 ID를 [동기화하기 위해 수행됩니다](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html).
