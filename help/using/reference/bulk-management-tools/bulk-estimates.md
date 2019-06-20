---
description: 벌크 예상은 세그먼트 규칙을 기반으로 한 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 벌크 예측 요청을 만듭니다.
seo-description: 벌크 예상은 세그먼트 규칙을 기반으로 한 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 벌크 예측 요청을 만듭니다.
seo-title: Bulk estimate
solution: Audience Manager
title: Bulk estimate
uuid: 63 B 2 F 06 A -8 BA 0-47 A 2-BD 0 B -8039 B 2 D 4 C 95 D
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Estimates{#bulk-estimates}

벌크 예상은 세그먼트 규칙을 기반으로 한 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 벌크 예측 요청을 만듭니다.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*는에서* 지원되지 [!DNL Audience Manager]않습니다. 이 도구는 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [UI에](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한이 [!DNL Audience Manager] 에서 [!UICONTROL Bulk Management Tools]인정됩니다.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. **[!UICONTROL Headers]** 탭을 클릭하고 [!UICONTROL Estimate Segment Size] 헤더를 복사합니다.
1. **[!UICONTROL Estimate]** 탭을 클릭합니다.
1. 예상 헤더를 예측 워크시트의 첫 번째 행에 붙여넣습니다.
1. 머리글 레이블을 기반으로 해당 열에 변경할 데이터를 붙여넣거나 입력합니다.
1. 워크시트 도구 모음에서 업데이트할 항목과 일치하는 만들기 단추를 클릭합니다.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. 데이터를 입력하기 전에 벌크 예측 워크시트는 다음과 유사해야 합니다.

![](assets/estimate.png)일괄 업데이트가 오류를 반환하거나 실패하는 경우 일괄 관리 도구에 [대한 문제 해결을 참조하십시오](../../reference/bulk-management-tools/bulk-troubleshooting.md).

