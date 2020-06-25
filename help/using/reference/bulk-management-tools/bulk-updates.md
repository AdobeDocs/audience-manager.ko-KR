---
description: 벌크 업데이트를 사용하면 한 번의 작업으로 여러 세그먼트, 특성, 모델, 데이터 소스 및 세그먼트 또는 특성 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.
keywords: baaam
seo-description: 벌크 업데이트를 사용하면 한 번의 작업으로 여러 세그먼트, 특성, 모델, 데이터 소스 및 세그먼트 또는 특성 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.
seo-title: 벌크 업데이트
solution: Audience Manager
title: 벌크 업데이트
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---


# 벌크 업데이트{#bulk-updates}

벌크 업데이트를 사용하면 한 번의 작업으로 여러 세그먼트, 특성, 모델, 데이터 소스 및 세그먼트 또는 특성 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[UI에 할당된 RBAC 그룹 권한](../../features/administration/administration-overview.md) 은 [!DNL Audience Manager] 에서 유지됩니다 [!UICONTROL Bulk Management Tools].

벌크 업데이트를 수행하려면 워크시트를 열고 다음을 [!UICONTROL Bulk Management Tools] 수행합니다.

1. 탭을 **[!UICONTROL Headers]** 클릭하고 편집할 항목의 업데이트 헤더를 복사합니다.
2. Click the **[!UICONTROL Update]** tab.
3. 업데이트 워크시트의 첫 번째 행에 업데이트 머리글을 붙여넣습니다. 다음 사항에 주의하십시오.

   * 폴더를 업데이트할 때는 모든 머리글이 필요합니다.
   * 세그먼트 또는 트레이트를 업데이트할 때는 세그먼트 ID(SID)와 변경해야 하는 헤더 요소만 있으면 됩니다. 사용하지 않은 헤더를 삭제합니다.

4. 변경할 데이터를 헤더 레이블을 기준으로 해당 열로 붙여넣거나 입력합니다.
5. 워크시트 도구 모음에서 업데이트 중인 항목과 일치하는 업데이트 단추를 클릭합니다.
그러면 대화 상자가 [!UICONTROL Account Information] 열립니다.

6. 필요한 [로그온 정보를](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 제공하고 을 클릭합니다 **[!UICONTROL Submit]**.

   워크시트는 열을 [!UICONTROL Results] 만듭니다. 이 [!UICONTROL Results] 열은 성공적인 작업을 위해 JSON 응답을 반환합니다. 예제는 [REST API를](../../api/rest-api-main/rest-api-main.md) 참조하십시오. 데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 비슷해야 합니다.

![](assets/update.png)

벌크 업데이트에서 오류가 반환되거나 오류가 발생하면 벌크 관리 도구 [문제 해결을 참조하십시오](../../reference/bulk-management-tools/bulk-troubleshooting.md).
