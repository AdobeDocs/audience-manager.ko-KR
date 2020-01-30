---
description: 2019년 10월 14일경, 장치 ID 그래프에 대한 내 온보드 트레이트 모집단이 0으로 줄어들었다는 것을 발견했습니다. 이전에는 이 수가 훨씬 더 많았습니다.
seo-description: 2019년 10월 14일경, 장치 ID 그래프에 대한 내 온보드 트레이트 모집단이 0으로 줄어들었다는 것을 발견했습니다. 이전에는 이 수가 훨씬 더 많았습니다.
seo-title: 10월 15일경 온보딩 트레이트 인구가 0으로 떨어진 이유는 무엇입니까?
solution: Audience Manager
title: 10월 15일경 온보딩 트레이트 인구가 0으로 떨어진 이유는 무엇입니까?
translation-type: tm+mt
source-git-commit: eb129bbf642cb666ce3ea05ff606c051e02f4d1e

---


# 10월 15일경 온보딩 트레이트 인구가 0으로 떨어진 이유는 무엇입니까? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

2019년 10월 14일경, 장치 ID 그래프에 대한 내 온보드 트레이트 모집단이 0으로 줄어들었다는 것을 발견했습니다. 이전에는 이 수가 훨씬 더 많았습니다.

![장치 ID 드롭 이미지](/help/using/support-issues/assets/device_id_populationdrop.png)

**답변**

10월 15일, Audience Manager의 프로필 병합 규칙 기능에 대한 업데이트가 크로스 장치 데이터 소스에 업로드된 CRM ID의 온보드 데이터가 더 이상 장치 ID에 대해 실현되지 않는 위치로 변경되었습니다.  이전에는 Audience Manager가 크로스 장치 ID(또는 CRM ID)와 관련된 할당을 Audience Manager UUID(장치 ID)에 복사했을 뿐만 아니라 이를 구현했습니다.  트레이트 데이터의 특성과 실현되는 프로파일을 보다 정확하게 반영하기 위해 변경되었습니다.

트레이트 재연결을 보려면 트레이트 보기의 오른쪽 상단 모서리에 있는 드롭다운에서 &quot;장치 간 ID&quot; 옵션을 선택하십시오.

![장치 간 ID별 재할당 보기](/help/using/support-issues/assets/deviceid-crossdevice.png)

