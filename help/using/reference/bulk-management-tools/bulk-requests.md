---
description: 벌크 요청은 업데이트, 생성, 예측 및 삭제 워크시트의 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.
seo-description: 벌크 요청은 업데이트, 생성, 예측 및 삭제 워크시트의 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.
seo-title: 벌크 요청
solution: Audience Manager
title: 벌크 요청
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# 벌크 요청{#bulk-requests}

벌크 요청은 업데이트, 생성, 예측 및 삭제 워크시트의 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC 그룹 ](../../features/administration/administration-overview.md) 권한 [!DNL Audience Manager] 이 UI에 할당되어  [!UICONTROL Bulk Management Tools]있습니다.

[!UICONTROL Request] 워크시트에는 고유한 열 헤더 세트가 없으며 ID를 열에 복사할 필요가 없습니다. 대신 도구 모음에서 클릭하는 작업 버튼을 기반으로 데이터를 반환합니다. 또한 선택적 보고 기능은 픽셀 실행에 대한 빈도 수와 몇 개의 고정된 시간 간격에 대한 고유 사용자 수를 반환합니다.

벌크 요청을 수행하려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Request]** 탭을 클릭합니다.
2. 워크시트 상단의 도구 모음에서 작업할 데이터에 해당하는 요청 단추를 클릭합니다. 다음을 요청할 수 있습니다.

   * 알고리즘 모델
   * 데이터 소스
   * 파생 신호
   * 대상 매핑
   * 알고리즘, 규칙 기반 및 온보딩된 트레이트
   * 세그먼트
   * 트레이트 및 세그먼트 폴더 ID

   [!DNL Audience Manager] API는 벌크 데이터를 다시 [!UICONTROL Request] 워크시트에 기록합니다.

>[!NOTE]
>
>결과에서 `createTime` 및 `updateTime` 열은 데이터를 지수 표기법으로 반환합니다. 기본 날짜/시간 스탬프는 UNIX UTC 시간으로 기록됩니다. 현재 워크시트는 날짜/타임스탬프를 읽을 수 있는 형식으로 반환할 수 없습니다.

벌크 업데이트가 오류를 반환하거나 실패하면 [벌크 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하십시오.
