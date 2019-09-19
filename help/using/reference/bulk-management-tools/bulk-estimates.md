---
description: 대량 추정은 세그먼트 규칙을 기반으로 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 견적 요청을 수행합니다.
seo-description: 대량 추정은 세그먼트 규칙을 기반으로 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 견적 요청을 수행합니다.
seo-title: 대량 추정
solution: Audience Manager
title: 대량 추정
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 대량 추정{#bulk-estimates}

대량 추정은 세그먼트 규칙을 기반으로 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 견적 요청을 수행합니다.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>는 에서 [!UICONTROL Bulk Management Tools] 지원되지 *않습니다* . [!DNL Audience Manager] 이 도구는 편의를 위해 제공되는 무료 도구입니다. 일괄 변경의 경우 Audience Manager API를 [대신 사용하는 것이](../../api/rest-api-main/aam-api-getting-started.md) 좋습니다. [UI에 할당된 RBAC 그룹 권한은](../../features/administration/administration-overview.md) 에서 [!DNL Audience Manager] 적용됩니다 [!UICONTROL Bulk Management Tools].

벌크 업데이트를 하려면 워크시트를 열고 다음을 [!UICONTROL Bulk Management Tools] 수행합니다.

1. 탭을 **[!UICONTROL Headers]** 클릭하고 [!UICONTROL Estimate Segment Size] 헤더를 복사합니다.
1. Click the **[!UICONTROL Estimate]** tab.
1. 예상 워크시트의 첫 번째 행에 예측 헤더를 붙여 넣습니다.
1. 머리글 레이블을 기반으로 해당 열로 변경할 데이터를 붙여넣거나 입력합니다.
1. 워크시트 도구 모음에서 업데이트 중인 항목과 일치하는 만들기 단추를 클릭합니다.
이 작업을 수행하면 [!UICONTROL Account Information] 대화 상자가 열립니다.

1. 필요한 [로그온 정보를](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 제공하고 을 **[!UICONTROL Submit]**&#x200B;클릭합니다.

이 작업을 수행하면 워크시트에 예상 세그먼트 크기 데이터가 포함된 열이 만들어집니다. [!UICONTROL Response] 데이터를 입력하기 전에 벌크 예측 워크시트는 다음과 유사해야 합니다.

![](assets/estimate.png)
벌크 업데이트에서 오류가 반환되거나 오류가 발생하면 벌크 관리 [도구 문제 해결을 참조하십시오](../../reference/bulk-management-tools/bulk-troubleshooting.md).

