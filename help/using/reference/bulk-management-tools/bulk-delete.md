---
description: 일괄 삭제를 사용하면 한 번의 작업으로 여러 세그먼트, 특성, 폴더, 파생된 신호 및 대상을 제거할 수 있습니다. 다음 지침에 따라 일괄 삭제 요청을 수행합니다.
seo-description: 일괄 삭제를 사용하면 한 번의 작업으로 여러 세그먼트, 특성, 폴더, 파생된 신호 및 대상을 제거할 수 있습니다. 다음 지침에 따라 일괄 삭제 요청을 수행합니다.
seo-title: 일괄 삭제
solution: Audience Manager
title: 일괄 삭제
uuid: 679 CDE 46-09 FB -45 C 6-B 84 D -47 D -47 E 0 E 7 C 0 A
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Delete{#bulk-delete}

일괄 삭제를 사용하면 한 번의 작업으로 여러 세그먼트, 특성, 폴더, 파생된 신호 및 대상을 제거할 수 있습니다. 다음 지침에 따라 일괄 삭제 요청을 수행합니다.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*는에서* 지원되지 [!DNL Audience Manager]않습니다. 이 도구는 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [UI에](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한이 [!DNL Audience Manager] 에서 [!UICONTROL Bulk Management Tools]인정됩니다.

>[!NOTE]
>
>대상에 세그먼트가 매핑된 경우 대상 매핑에 대한 벌크 삭제가 실패합니다. 대상을 일괄 삭제하기 전에 사용자 인터페이스의 해당 대상에서 세그먼트를 제거합니다. 또한 트레이트 및 세그먼트 폴더는 삭제할 수 있으려면 비어 있어야 합니다.

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. **[!UICONTROL Headers]** 탭을 클릭하고 추가할 항목의 헤더를 복사합니다.
2. **[!UICONTROL Delete]** 탭을 클릭합니다.
3. 삭제 머리글을 업데이트 워크시트의 첫 번째 행에 붙여넣습니다.
4. 머리글 아래 열에서 삭제하려는 개체의 ID를 붙여넣거나 입력합니다.
5. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 열은 항목이 삭제되었는지 또는 오류 메시지가 표시되는지를 나타내는 메시지를 반환합니다.
데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 유사해야 합니다.

![](assets/delete.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
