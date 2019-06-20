---
description: 일괄 업데이트를 사용하면 여러 세그먼트, 특성, 세그먼트 또는 트레이트 폴더 요소를 한 번에 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.
keywords: Baaam
seo-description: 일괄 업데이트를 사용하면 여러 세그먼트, 특성, 세그먼트 또는 트레이트 폴더 요소를 한 번에 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.
seo-title: 벌크 업데이트
solution: Audience Manager
title: 벌크 업데이트
uuid: 22 F 1 badd-A 274-4 D 3 E -9957-A 24 BF 8 C 1 D 0 DC
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Updates{#bulk-updates}

일괄 업데이트를 사용하면 여러 세그먼트, 특성, 세그먼트 또는 트레이트 폴더 요소를 한 번에 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*는에서* 지원되지 [!DNL Audience Manager]않습니다. 이 도구는 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [UI에](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한이 [!DNL Audience Manager] 에서 [!UICONTROL Bulk Management Tools]인정됩니다.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. **[!UICONTROL Headers]** 탭을 클릭하고 편집할 항목의 업데이트 헤더를 복사합니다.
1. **[!UICONTROL Update]** 탭을 클릭합니다.
1. 업데이트 헤더를 업데이트 워크시트의 첫 번째 행에 붙여넣습니다. 다음을 참고하십시오.

   * 폴더를 업데이트할 때는 모든 헤더가 필요합니다.
   * 세그먼트나 트레이트를 업데이트할 때 세그먼트 ID (SID) 와 변경해야 하는 헤더 요소만 있으면 됩니다. 사용하지 않은 헤더를 삭제합니다.

1. 머리글 레이블을 기반으로 해당 열에 변경할 데이터를 붙여넣거나 입력합니다.
1. 워크시트 도구 모음에서 업데이트할 항목과 일치하는 업데이트 단추를 클릭합니다.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 열은 성공적인 작업에 대한 JSON 응답을 반환합니다. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. 데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 유사해야 합니다.

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
