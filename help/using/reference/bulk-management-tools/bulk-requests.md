---
description: 벌크 요청은 워크시트의 업데이트, 작성, 견적 및 삭제 시 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.
seo-description: 벌크 요청은 워크시트의 업데이트, 작성, 견적 및 삭제 시 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.
seo-title: 대량 요청
solution: Audience Manager
title: 대량 요청
uuid: 0192 D 26 A -4 CEA -4 E 12-9 FEA -388 B 92 B 382 F 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Requests{#bulk-requests}

벌크 요청은 워크시트의 업데이트, 작성, 견적 및 삭제 시 다른 헤더와 함께 사용할 수 있는 데이터를 반환합니다.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*는에서* 지원되지 [!DNL Audience Manager]않습니다. 이 도구는 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [UI에](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한이 [!DNL Audience Manager] 에서 [!UICONTROL Bulk Management Tools]인정됩니다.

[!UICONTROL Request] 워크시트에는 자체 열 헤더 세트가 없으므로 어떤 열에도 ID를 복사할 필요가 없습니다. 대신, 도구 모음에서 클릭하는 작업 단추를 기반으로 데이터를 반환합니다. 또한 선택적 보고 기능은 여러 고정 시간 간격에 대한 픽셀 수 및 고유 사용자 수에 대한 빈도 수를 반환합니다.

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. **[!UICONTROL Request]** 탭을 클릭합니다.
2. 워크시트 상단의 도구 모음에서 작업할 데이터에 해당하는 요청 단추를 클릭합니다. 다음을 요청할 수 있습니다.

   * 데이터 공급자 ID
   * 파생 신호
   * 대상 매핑
   * 규칙 기반 및 온보드 트레이닝
   * 세그먼트
   * 특성 및 세그먼트 폴더 ID
   [!DNL Audience Manager] API는 [!UICONTROL Request] 워크시트로 대량의 데이터를 다시 씁니다.

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. 기본 날짜/타임스탬프는 UNIX UTC 시간으로 기록됩니다. 현재, 워크시트는 날짜/타임스탬프를 읽을 수 있는 형식으로 반환할 수 없습니다.

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
