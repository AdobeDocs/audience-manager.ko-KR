---
description: 벌크 추정은 세그먼트 규칙에 따라 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 견적 요청을 수행합니다.
seo-description: 벌크 추정은 세그먼트 규칙에 따라 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 견적 요청을 수행합니다.
seo-title: 벌크 예상
solution: Audience Manager
title: 벌크 예상
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# 벌크 예상{#bulk-estimates}

벌크 추정은 세그먼트 규칙에 따라 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 대량 견적 요청을 수행합니다.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[UI](../../features/administration/administration-overview.md) 에 할당된 RBAC 그룹  [!DNL Audience Manager]   [!UICONTROL Bulk Management Tools]권한은

벌크 업데이트를 수행하려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Headers]** 탭을 클릭하고 [!UICONTROL Estimate Segment Size] 헤더를 복사합니다.
2. **[!UICONTROL Estimate]** 탭을 클릭합니다.
3. 예상 워크시트의 첫 번째 행에 추정 헤더를 붙여넣습니다.
4. 변경할 데이터를 머리글 레이블을 기반으로 해당 열로 붙여넣거나 입력합니다.
5. 워크시트 도구 모음에서 업데이트 중인 항목과 일치하는 만들기 단추를 클릭합니다.
이 작업을 수행하면 [!UICONTROL Account Information] 대화 상자가 열립니다.
6. 필수 [로그온 정보](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)를 입력하고 **[!UICONTROL Submit]**&#x200B;를 클릭합니다.

이 작업은 예상 세그먼트 크기 데이터가 포함된 워크시트에서 [!UICONTROL Response] 열을 만듭니다. 데이터를 입력하기 전에 벌크 예측 워크시트는 다음과 비슷해야 합니다.

![](assets/estimate.png)
벌크 업데이트에서 오류가 반환되거나 오류가 발생하면 벌크 관리 도구  [문제 해결을 참조하십시오](../../reference/bulk-management-tools/bulk-troubleshooting.md).
