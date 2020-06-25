---
description: 벌크 추정은 세그먼트 규칙에 따라 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 예상 요청을 수행합니다.
seo-description: 벌크 추정은 세그먼트 규칙에 따라 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 예상 요청을 수행합니다.
seo-title: 벌크 예상
solution: Audience Manager
title: 벌크 예상
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# 벌크 예상{#bulk-estimates}

벌크 추정은 세그먼트 규칙에 따라 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 예상 요청을 수행합니다.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[UI에 할당된 RBAC 그룹 권한](../../features/administration/administration-overview.md) 은 [!DNL Audience Manager] 에서 유지됩니다 [!UICONTROL Bulk Management Tools].

벌크 업데이트를 수행하려면 워크시트를 열고 다음을 [!UICONTROL Bulk Management Tools] 수행합니다.

1. 탭을 **[!UICONTROL Headers]** 클릭하고 [!UICONTROL Estimate Segment Size] 헤더를 복사합니다.
2. Click the **[!UICONTROL Estimate]** tab.
3. 예상 워크시트의 첫 번째 행에 예측 헤더를 붙여넣습니다.
4. 변경할 데이터를 헤더 레이블을 기준으로 해당 열로 붙여넣거나 입력합니다.
5. 워크시트 도구 모음에서 업데이트 중인 항목과 일치하는 만들기 단추를 클릭합니다.
그러면 대화 상자가 [!UICONTROL Account Information] 열립니다.
6. 필요한 [로그온 정보를](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 제공하고 을 클릭합니다 **[!UICONTROL Submit]**.

이 작업을 수행하면 워크시트의 예상 세그먼트 크기 데이터가 포함된 열이 만들어집니다. [!UICONTROL Response] 데이터를 입력하기 전에 벌크 예측 워크시트는 다음과 비슷해야 합니다.

![](assets/estimate.png)
벌크 업데이트에서 오류가 반환되거나 오류가 발생하면 벌크 관리 도구 [문제 해결을 참조하십시오](../../reference/bulk-management-tools/bulk-troubleshooting.md).

