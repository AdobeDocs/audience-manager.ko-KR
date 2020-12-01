---
description: 벌크 요청은 업데이트, 생성, 예측 및 삭제 워크시트에서 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.
seo-description: 벌크 요청은 업데이트, 생성, 예측 및 삭제 워크시트에서 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.
seo-title: 벌크 요청
solution: Audience Manager
title: 벌크 요청
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# 벌크 요청{#bulk-requests}

벌크 요청은 업데이트, 생성, 예측 및 삭제 워크시트에서 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[UI에 ](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한 [!DNL Audience Manager] 은 에서 유지됩니다 [!UICONTROL Bulk Management Tools].

[!UICONTROL Request] 워크시트에는 자체 열 머리글이 없으며 ID를 열에 복사할 필요가 없습니다. 대신 도구 모음에서 클릭하는 작업 단추를 기반으로 데이터를 반환합니다. 또한 선택 사항 보고 기능은 몇 가지 고정 시간 간격에 대해 픽셀 화재에 대한 빈도 수 및 고유 사용자 수를 반환합니다.

벌크 요청을 하려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Request]** 탭을 클릭합니다.
2. 워크시트 맨 위의 도구 모음에서 작업할 데이터에 해당하는 요청 단추를 클릭합니다. 다음을 요청할 수 있습니다.

   * 알고리즘 모델
   * 데이터 소스
   * 파생 신호
   * 대상 매핑
   * 알고리즘, 규칙 기반, 온보드 트레이트
   * 세그먼트
   * 특성 및 세그먼트 폴더 ID

   [!DNL Audience Manager] API는 벌크 데이터를 다시 [!UICONTROL Request] 워크시트에 기록합니다.

>[!NOTE]
>
>결과에서 `createTime` 및 `updateTime` 열은 데이터를 지수 표기법으로 반환합니다. 기본 날짜/시간 스탬프는 UNIX UTC 시간으로 기록됩니다. 현재 워크시트는 날짜/시간 스탬프를 읽을 수 있는 형식으로 반환할 수 없습니다.

벌크 업데이트에서 오류가 반환되거나 오류가 발생하면 [벌크 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하십시오.
