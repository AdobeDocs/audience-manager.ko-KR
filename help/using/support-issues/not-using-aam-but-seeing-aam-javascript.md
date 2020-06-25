---
description: Audience Manager를 사용하고 있지 않은데 Javascript 디버거에 Audience Manager Javascript 호출이 표시됩니다. 왜입니까?
seo-description: 사용하고 있지 않은데 Javascript 디버거에 Audience Manager Javascript 호출이 표시됩니다. 왜입니까?
seo-title: Audience Manager를 사용하고 있지 않은데 Javascript 디버거에 Audience Manager Javascript 호출이 표시됩니다. 왜입니까?
solution: Audience Manager
title: Audience Manager를 사용하고 있지 않은데 Javascript 디버거에 Audience Manager Javascript 호출이 표시됩니다. 왜입니까?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 100%

---


# Audience Manager 고객이 아닌데 당사 사이트에 Audience Manager Javascript 호출이 표시됩니다

## 질문

Adobe Audience Manager를 사용하고 있지 않은데 Javascript 디버거에 Audience Manager Javascript 호출이 표시됩니다.

왜 이런 일이 발생합니까?

## 답변

귀사의 자산에서 [Experience Cloud ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html)를 실행 중일 수 있습니다. 그럴 경우 이 Audience Manager 참조가 있는 것이 반드시 자산에서 Audience Manager를 실행 중임을 나타내지는 않습니다. 대신 Audience Manager가 이 서비스를 실행하고 있음을 의미합니다.

일반적으로 Audience Manager 서버 호출은 [고객 ID를 동기화](https://docs.adobe.com/content/help/ko-KR/id-service/using/id-service-api/methods/setcustomerids.html)하기 위해 수행됩니다.
