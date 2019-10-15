---
description: 일괄 업데이트를 사용하면 하나의 작업에서 여러 세그먼트, 트레이트, 모델, 데이터 소스 및 세그먼트 또는 트레이트 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.
keywords: aam
seo-description: 일괄 업데이트를 사용하면 하나의 작업에서 여러 세그먼트, 트레이트, 모델, 데이터 소스 및 세그먼트 또는 트레이트 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.
seo-title: 일괄 업데이트
solution: Audience Manager
title: 일괄 업데이트
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: 30d4cec4502a2cf8b217816ea4ae62eb1b22f641

---


# 일괄 업데이트{#bulk-updates}

일괄 업데이트를 사용하면 하나의 작업에서 여러 세그먼트, 트레이트, 모델, 데이터 소스 및 세그먼트 또는 트레이트 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>는 에서 [!UICONTROL Bulk Management Tools] 지원되지 *않습니다* . [!DNL Audience Manager] 이 도구는 편의를 위해 제공되는 무료 도구입니다. 일괄 변경의 경우 Audience Manager API를 [대신 사용하는 것이](../../api/rest-api-main/aam-api-getting-started.md) 좋습니다. [UI에 할당된 RBAC 그룹 권한은](../../features/administration/administration-overview.md) 에서 [!DNL Audience Manager] 적용됩니다 [!UICONTROL Bulk Management Tools].

벌크 업데이트를 하려면 워크시트를 열고 다음을 [!UICONTROL Bulk Management Tools] 수행합니다.

1. 탭을 클릭하고 편집할 항목에 대한 업데이트 헤더를 복사합니다. **[!UICONTROL Headers]**
1. Click the **[!UICONTROL Update]** tab.
1. 업데이트 워크시트의 첫 번째 행에 업데이트 머리글을 붙여넣습니다. 다음 사항에 주의하십시오.

   * 폴더를 업데이트할 때는 모든 머리글이 필요합니다.
   * 세그먼트나 트레이트를 업데이트할 때는 세그먼트 ID(SID)와 변경해야 하는 헤더 요소만 있으면 됩니다. 사용하지 않은 머리글을 삭제합니다.

1. 머리글 레이블을 기반으로 해당 열로 변경할 데이터를 붙여넣거나 입력합니다.
1. 워크시트 도구 모음에서 업데이트 중인 항목과 일치하는 업데이트 단추를 클릭합니다.
이 작업을 수행하면 [!UICONTROL Account Information] 대화 상자가 열립니다.

1. 필요한 [로그온 정보를](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 제공하고 을 **[!UICONTROL Submit]**&#x200B;클릭합니다.

   워크시트는 [!UICONTROL Results] 열을 만듭니다. 이 [!UICONTROL Results] 열은 성공적인 작업에 대한 JSON 응답을 반환합니다. 예제는 REST [API를](../../api/rest-api-main/rest-api-main.md) 참조하십시오. 데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 유사해야 합니다.

![](assets/update.png)

벌크 업데이트에서 오류가 반환되거나 오류가 발생하면 벌크 관리 [도구 문제 해결을 참조하십시오](../../reference/bulk-management-tools/bulk-troubleshooting.md).
