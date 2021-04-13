---
description: 벌크 삭제를 사용하면 단일 작업으로 여러 세그먼트, 트레이트, 폴더, 파생 신호, 데이터 소스, 모델 및 대상을 제거할 수 있습니다. 다음 지침에 따라 대량 삭제 요청을 수행합니다.
seo-description: 벌크 삭제를 사용하면 단일 작업으로 여러 세그먼트, 트레이트, 폴더, 파생 신호, 데이터 소스, 모델 및 대상을 제거할 수 있습니다. 다음 지침에 따라 대량 삭제 요청을 수행합니다.
seo-title: 벌크 삭제
solution: Audience Manager
title: 벌크 삭제
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# 벌크 삭제{#bulk-delete}

벌크 삭제를 사용하면 단일 작업으로 여러 세그먼트, 트레이트, 폴더, 파생 신호, 데이터 소스, 모델 및 대상을 제거할 수 있습니다. 다음 지침에 따라 대량 삭제 요청을 수행합니다.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[UI](../../features/administration/administration-overview.md) 에 할당된 RBAC 그룹  [!DNL Audience Manager]   [!UICONTROL Bulk Management Tools]권한은

>[!NOTE]
>
>대상에 매핑된 세그먼트가 있는 경우 대상 매핑에 대한 벌크 삭제가 실패합니다. 대상을 벌크 삭제하기 전에 사용자 인터페이스에서 해당 대상에서 세그먼트를 제거합니다. 또한 트레이트 및 세그먼트 폴더를 삭제하려면 먼저 비워 두어야 합니다.

여러 항목을 삭제하려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Headers]** 탭을 클릭하고 추가할 항목의 만들기 헤더를 복사합니다.
2. **[!UICONTROL Delete]** 탭을 클릭합니다.
3. 업데이트 워크시트의 첫 번째 행에 delete 헤더를 붙여넣습니다.
4. 머리글 아래의 열에서 삭제할 개체의 ID를 붙여넣거나 입력합니다.
5. 필수 [로그온 정보](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)를 입력하고 **[!UICONTROL Submit]**&#x200B;를 클릭합니다.

   워크시트는 [!UICONTROL Results] 열을 만듭니다. [!UICONTROL Results] 열은 항목이 삭제되었는지 또는 오류 메시지를 나타내는 메시지를 반환합니다.
데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 비슷해야 합니다.

![](assets/delete.png)

벌크 업데이트가 오류를 반환하거나 실패하는 경우 [벌크 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하십시오.
