---
description: 벌크 예측은 세그먼트 규칙을 기반으로 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 일괄 견적 요청을 수행합니다.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: 벌크 예상
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# 벌크 예상{#bulk-estimates}

벌크 예측은 세그먼트 규칙을 기반으로 세그먼트 크기 데이터를 반환합니다. 다음 지침에 따라 일괄 견적 요청을 수행합니다.

>[!IMPORTANT]
>
>벌크 관리 도구는 공식적으로 지원되는 Adobe 제품이 아닙니다. 고객 지원 센터를 통한 문제 해결 및 지원은 사안별로 처리됩니다.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[&#x200B; UI에 할당된 &#x200B;](../../features/administration/administration-overview.md)RBAC 그룹 권한[!DNL Audience Manager]이(가) [!UICONTROL Bulk Management Tools]에서 허용됩니다.

대량 업데이트하려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Headers]** 탭을 클릭하고 [!UICONTROL Estimate Segment Size] 헤더를 복사합니다.
2. **[!UICONTROL Estimate]** 탭을 클릭합니다.
3. 예상 워크시트의 첫 행에 예상 헤더를 붙여 넣습니다.
4. 변경할 데이터를 헤더 레이블을 기반으로 해당 열에 붙여넣거나 입력합니다.
5. 워크시트 도구 모음에서 업데이트할 항목과 일치하는 생성 단추를 클릭합니다.
이 작업은 [!UICONTROL Account Information] 대화 상자를 엽니다.
6. 필요한 [정보에 대한 로그](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)를 입력하고 **[!UICONTROL Submit]**&#x200B;을(를) 클릭합니다.

이 작업을 수행하면 워크시트에 예상 세그먼트 크기 데이터가 포함된 [!UICONTROL Response] 열이 만들어집니다. 데이터를 입력하기 전에 벌크 예상 워크시트는 다음과 유사해야 합니다.

![](assets/estimate.png)
벌크 업데이트가 오류를 반환하거나 실패한 경우 [벌크 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하십시오.
