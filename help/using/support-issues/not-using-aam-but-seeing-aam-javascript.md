---
description: Audience Manager를 사용하고 있지 않지만 Javascript 디버거에 Audience Manager Javascript 호출이 있습니다. - 이유는 무엇입니까?
seo-description: Adobe는 사용하고 있지 않지만 JavaScript 디버거에 Audience Manager Javascript 호출이 포함되어 있습니다 - 이유는 무엇입니까?
seo-title: Audience Manager를 사용하고 있지 않지만 Javascript 디버거에 Audience Manager Javascript 호출이 있습니다. - 이유는 무엇입니까?
solution: Audience Manager
title: Audience Manager를 사용하고 있지 않지만 Javascript 디버거에 Audience Manager Javascript 호출이 있습니다. - 이유는 무엇입니까?
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# Adobe는 Audience Manager 고객이 아니지만 사이트에서 Audience Manager Javascript 호출을 참조하십시오.

## 질문

Adobe Audience Manager를 사용하고 있지 않지만 Javascript 디버거에서는 Audience Manager Javascript 호출이 표시됩니다.  왜 이런 일이 벌어질까?

## 답변

속성에서 방문자 ID 서비스를 실행 중일 수 있습니다. 이 경우 AAM 참조가 Audience Manager를 실행 중인 속성을 반드시 참조하지는 않지만 Audience Manager가 실제로 이 서비스를 구현한다는 것을 의미합니다.

AAM 호출은 일반적으로 설정 고객 ID를 동기화하기 위해 수행됩니다.
