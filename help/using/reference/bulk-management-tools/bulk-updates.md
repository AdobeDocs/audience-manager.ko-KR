---
description: 벌크 업데이트를 사용하면 한 번에 여러 세그먼트, 트레이트, 모델, 데이터 소스 및 세그먼트 또는 트레이트 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.
keywords: aam
seo-description: 벌크 업데이트를 사용하면 한 번에 여러 세그먼트, 트레이트, 모델, 데이터 소스 및 세그먼트 또는 트레이트 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.
seo-title: 벌크 업데이트
solution: Audience Manager
title: 벌크 업데이트
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# 벌크 업데이트{#bulk-updates}

벌크 업데이트를 사용하면 한 번에 여러 세그먼트, 트레이트, 모델, 데이터 소스 및 세그먼트 또는 트레이트 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 일괄 업데이트를 수행합니다.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[UI](../../features/administration/administration-overview.md) 에 할당된 RBAC 그룹  [!DNL Audience Manager]   [!UICONTROL Bulk Management Tools]권한은

벌크 업데이트를 수행하려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Headers]** 탭을 클릭하고 편집할 항목의 업데이트 헤더를 복사합니다.
2. **[!UICONTROL Update]** 탭을 클릭합니다.
3. 업데이트 워크시트의 첫 번째 행에 업데이트 헤더를 붙여넣습니다. 다음 사항에 주의하십시오.

   * 폴더를 업데이트할 때 모든 머리글이 필요합니다.
   * 세그먼트나 트레이트를 업데이트할 때는 세그먼트 ID(SID) 및 변경해야 하는 헤더 요소만 있으면 됩니다. 사용하지 않은 헤더를 삭제합니다.

4. 변경할 데이터를 머리글 레이블을 기반으로 해당 열로 붙여넣거나 입력합니다.
5. 워크시트 도구 모음에서        업데이트할 항목.
이 작업을 수행하면 [!UICONTROL Account Information] 대화 상자가 열립니다.

6. 필수 [로그온 정보](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)를 입력하고 **[!UICONTROL Submit]**&#x200B;를 클릭합니다.

   워크시트는 [!UICONTROL Results] 열을 만듭니다. [!UICONTROL Results] 열은 성공적인 작업에 대한 JSON 응답을 반환합니다. 예제는 [REST API](../../api/rest-api-main/rest-api-main.md)를 참조하십시오. 데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 비슷해야 합니다.

![](assets/update.png)

벌크 업데이트가 오류를 반환하거나 실패하는 경우 [벌크 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하십시오.
