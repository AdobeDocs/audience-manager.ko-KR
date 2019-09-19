---
description: 벌크 만들기를 사용하면 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트 및 기타 항목을 하나의 작업으로 구성할 수 있습니다. 다음 지침에 따라 일괄 작성 요청을 수행합니다.
seo-description: 벌크 만들기를 사용하면 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트 및 기타 항목을 하나의 작업으로 구성할 수 있습니다. 다음 지침에 따라 일괄 작성 요청을 수행합니다.
seo-title: 벌크 만들기
solution: Audience Manager
title: 벌크 만들기
uuid: 1e09bcfa-78 파섹
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 벌크 만들기{#bulk-create}

벌크 만들기를 사용하면 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트 및 기타 항목을 하나의 작업으로 구성할 수 있습니다. 다음 지침에 따라 일괄 작성 요청을 수행합니다.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>는 에서 [!UICONTROL Bulk Management Tools] 지원되지 *않습니다* . [!DNL Audience Manager] 이 도구는 편의를 위해 제공되는 무료 도구입니다. 일괄 변경의 경우 Audience Manager API를 [대신 사용하는 것이](../../api/rest-api-main/aam-api-getting-started.md) 좋습니다. [UI에 할당된 RBAC 그룹 권한은](../../features/administration/administration-overview.md) 에서 [!DNL Audience Manager] 적용됩니다 [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>벌크 작성 요청에서 개체 유형을 혼합하지 마십시오. 각 개체의 헤더는 고유하며 결합할 수 없습니다. 워크시트를 지우고 다른 항목에 대해 별도로 요청합니다.

개체를 대량으로 만들려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. 탭을 **[!UICONTROL Headers]** 클릭하고 추가할 항목의 만들기 머리글을 복사합니다.
1. Click the **[!UICONTROL Create]** tab.
1. create 헤더를 업데이트 워크시트의 첫 번째 행에 붙여넣습니다.
1. 머리글 레이블을 기반으로 해당 열로 변경할 데이터를 붙여넣거나 입력합니다.
1. 워크시트 도구 모음에서 업데이트 중인 항목과 일치하는 만들기 단추를 클릭합니다.
이 작업을 수행하면 [!UICONTROL Account Information] 대화 상자가 열립니다.

1. 필요한 [로그온 정보를](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 제공하고 을 **[!UICONTROL Submit]**&#x200B;클릭합니다.

워크시트는 [!UICONTROL Results] 열을 만듭니다. 이 [!UICONTROL Results] 열은 성공적인 작업에 대한 JSON 응답을 반환합니다. 예제는 REST [API를](../../api/rest-api-main/rest-api-main.md) 참조하십시오. 데이터를 입력하기 전에 벌크 작성 워크시트는 다음 예와 유사해야 합니다. 여기에 서로 다른 모든 만들기 옵션이 표시되지 않습니다. 여기에는 완료된 워크시트가 어떤 모습인지 이해하는 데 도움이 됩니다.

![](assets/cretetraits.png)


벌크 업데이트에서 오류가 반환되거나 오류가 발생하면 벌크 관리 [도구 문제 해결을 참조하십시오](../../reference/bulk-management-tools/bulk-troubleshooting.md).
