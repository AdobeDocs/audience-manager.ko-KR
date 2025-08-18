---
description: 일괄 삭제를 사용하면 한 번의 작업으로 여러 세그먼트, 트레이트, 폴더, 파생된 신호, 데이터 소스, 모델 및 대상을 제거할 수 있습니다. 대량 삭제를 요청하려면 다음 지침을 따르십시오.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: 일괄 삭제
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# 일괄 삭제{#bulk-delete}

일괄 삭제를 사용하면 한 번의 작업으로 여러 세그먼트, 트레이트, 폴더, 파생된 신호, 데이터 소스, 모델 및 대상을 제거할 수 있습니다. 대량 삭제를 요청하려면 다음 지침을 따르십시오.

>[!IMPORTANT]
>
>벌크 관리 도구는 공식적으로 지원되는 Adobe 제품이 아닙니다. 고객 지원 센터를 통한 문제 해결 및 지원은 사안별로 처리됩니다.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[ UI에 할당된 ](../../features/administration/administration-overview.md)RBAC 그룹 권한[!DNL Audience Manager]이(가) [!UICONTROL Bulk Management Tools]에서 허용됩니다.

>[!NOTE]
>
>대상에 매핑된 세그먼트가 있는 경우 대상 매핑에 대한 대량 삭제가 실패합니다. 대상을 일괄 삭제하기 전에 사용자 인터페이스의 해당 대상에서 세그먼트를 제거합니다. 또한 트레이트 및 세그먼트 폴더를 삭제하려면 먼저 비어 있어야 합니다.

여러 항목을 삭제하려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Headers]** 탭을 클릭하고 추가하려는 항목의 만들기 헤더를 복사합니다.
2. **[!UICONTROL Delete]** 탭을 클릭합니다.
3. 삭제 헤더를 업데이트 워크시트의 첫 행에 붙여넣습니다.
4. 헤더 아래 열에 삭제할 오브젝트의 ID를 붙여 넣거나 입력합니다.
5. 필요한 [정보에 대한 로그](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)를 입력하고 **[!UICONTROL Submit]**&#x200B;을(를) 클릭합니다.

   워크시트에서 [!UICONTROL Results] 열을 만듭니다. [!UICONTROL Results] 열은 항목이 삭제되었는지 또는 오류 메시지를 나타내는 메시지를 반환합니다.
데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 유사해야 합니다.

![](assets/delete.png)

벌크 업데이트가 오류를 반환하거나 실패한 경우 [대량 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하세요.
