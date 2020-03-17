---
description: 벌크 삭제를 사용하면 한 번의 작업으로 여러 세그먼트, 트레이트, 폴더, 파생 신호, 데이터 소스, 모델 및 대상을 제거할 수 있습니다. 다음 지침에 따라 대량 삭제를 요청합니다.
seo-description: 벌크 삭제를 사용하면 한 번의 작업으로 여러 세그먼트, 트레이트, 폴더, 파생 신호, 데이터 소스, 모델 및 대상을 제거할 수 있습니다. 다음 지침에 따라 대량 삭제를 요청합니다.
seo-title: 벌크 삭제
solution: Audience Manager
title: 벌크 삭제
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# 벌크 삭제{#bulk-delete}

벌크 삭제를 사용하면 한 번의 작업으로 여러 세그먼트, 트레이트, 폴더, 파생 신호, 데이터 소스, 모델 및 대상을 제거할 수 있습니다. 다음 지침에 따라 대량 삭제를 요청합니다.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[UI에 할당된 RBAC 그룹 권한은](../../features/administration/administration-overview.md) 에서 [!DNL Audience Manager] 적용됩니다 [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>대상에 매핑된 세그먼트가 있는 경우 대상 매핑에 대한 벌크 삭제가 실패합니다. 대상을 벌크 삭제하기 전에 사용자 인터페이스의 해당 대상에서 세그먼트를 제거합니다. 또한 트레이트 및 세그먼트 폴더를 삭제하려면 먼저 비어 있어야 합니다.

여러 항목을 삭제하려면 워크시트를 열고 다음을 [!UICONTROL Bulk Management Tools] 수행합니다.

1. 탭을 **[!UICONTROL Headers]** 클릭하고 추가할 항목의 만들기 머리글을 복사합니다.
2. Click the **[!UICONTROL Delete]** tab.
3. 업데이트 워크시트의 첫 번째 행에 삭제 머리글을 붙여넣습니다.
4. 머리글 아래 열에 삭제할 개체의 ID를 붙여넣거나 입력합니다.
5. 필요한 [로그온 정보를](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 제공하고 을 **[!UICONTROL Submit]**&#x200B;클릭합니다.

   워크시트는 [!UICONTROL Results] 열을 만듭니다. 이 [!UICONTROL Results] 열에는 항목이 삭제되었는지 또는 오류 메시지가 표시됩니다.
데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 유사해야 합니다.

![](assets/delete.png)

벌크 업데이트에서 오류가 반환되거나 오류가 발생하면 벌크 관리 [도구 문제 해결을 참조하십시오](../../reference/bulk-management-tools/bulk-troubleshooting.md).
