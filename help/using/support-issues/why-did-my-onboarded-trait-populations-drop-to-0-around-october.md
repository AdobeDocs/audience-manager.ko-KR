---
description: 2019년 10월 14일쯤, 장치 ID 그래프에 대한 내 온보딩된 트레이트 인구가 0으로 줄어든 것을 발견했습니다. 이전에는 훨씬 더 높았습니다.
seo-description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-title: Why did my Onboarded trait populations drop to 0 around October 15th?
solution: Audience Manager
title: 10월 15일경 온보딩된 트레이트 인구가 0으로 떨어진 이유는 무엇입니까?
feature: Support
exl-id: e93cee15-7d05-4f81-8f14-a3e03f214542
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 100%

---

# 10월 15일경 온보딩된 트레이트 인구가 0으로 떨어진 이유는 무엇입니까? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## 질문

2019년 10월 14일쯤, 장치 ID 그래프에 대한 내 온보딩된 트레이트 인구가 0으로 줄어든 것을 발견했습니다. 이전에는 훨씬 더 높았습니다. 이런 일이 일어난 이유는 무엇입니까?

![장치 ID 감소 이미지](assets/device_id_populationdrop.png)

## 답변

10월 15일, Audience Manager의 프로필 병합 규칙 기능이 업데이트되어, 교차 장치 데이터 소스에 업로드된 CRM ID을 키로 사용하는 온보딩된 데이터가 더 이상 장치 ID에 대해 실현되지 않습니다.  이전에는 Audience Manager가 교차 장치 ID(또는 CRM ID)에 대해 실현하고 이러한 실현을 연관된 Audience Manager UUID(Device ID)에도 복사했습니다.  실현되는 트레이트 데이터와 프로필의 특성을 더 정확하게 반영하기 위해 변경 작업이 수행되었습니다.

트레이트 실현을 보려면 트레이트 보기의 오른쪽 상단 모서리에 있는 드롭다운에서 &quot;Cross-Device ID&quot; 옵션을 선택하십시오.

![교차 장치 ID별 실현 보기](assets/deviceid-crossdevice.png)
