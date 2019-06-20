---
description: 일괄 만들기를 사용하면 단일 작업으로 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트레이트 및 기타 항목을 만들 수 있습니다. 다음 지침에 따라 벌크 작성 요청을 수행하십시오.
seo-description: 일괄 만들기를 사용하면 단일 작업으로 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트레이트 및 기타 항목을 만들 수 있습니다. 다음 지침에 따라 벌크 작성 요청을 수행하십시오.
seo-title: 벌크 제작
solution: Audience Manager
title: 벌크 제작
uuid: 1 E 09 BCFA -783 E -4 E 9 B -9 EAD -147 F 8 D 1381 C 8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Create{#bulk-create}

일괄 만들기를 사용하면 단일 작업으로 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트레이트 및 기타 항목을 만들 수 있습니다. 다음 지침에 따라 벌크 작성 요청을 수행하십시오.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*는에서* 지원되지 [!DNL Audience Manager]않습니다. 이 도구는 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [UI에](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한이 [!DNL Audience Manager] 에서 [!UICONTROL Bulk Management Tools]인정됩니다.

>[!CAUTION]
>
>벌크 작성 요청에서 개체 유형을 혼합하지 마십시오. 각 개체의 헤더는 고유하므로 결합할 수 없습니다. 워크시트를 지우고 다른 항목에 대한 별도의 요청을 만듭니다.

To create objects in bulk, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. **[!UICONTROL Headers]** 탭을 클릭하고 추가할 항목의 헤더를 복사합니다.
1. **[!UICONTROL Create]** 탭을 클릭합니다.
1. Create headers into the first row of the update worksheet.
1. 머리글 레이블을 기반으로 해당 열에 변경할 데이터를 붙여넣거나 입력합니다.
1. 워크시트 도구 모음에서 업데이트할 항목과 일치하는 만들기 단추를 클릭합니다.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 열은 성공적인 작업에 대한 JSON 응답을 반환합니다. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. 데이터를 입력하기 전에 벌크 만들기 워크시트는 다음 예와 유사해야 합니다. 여기서는 다른 만들기 옵션이 모두 여기에 표시되지 않습니다. 완료된 워크시트의 모양을 이해하는 데 도움이 됩니다.

![](assets/cretetraits.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
