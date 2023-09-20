---
description: 벌크 업데이트를 사용하면 한 번의 작업으로 여러 세그먼트, 트레이트, 모델, 데이터 소스, 세그먼트 또는 트레이트 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 벌크 업데이트를 수행합니다.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: 벌크 업데이트
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# 벌크 업데이트{#bulk-updates}

벌크 업데이트를 사용하면 한 번의 작업으로 여러 세그먼트, 트레이트, 모델, 데이터 소스, 세그먼트 또는 트레이트 폴더 요소를 편집할 수 있습니다. 다음 지침에 따라 벌크 업데이트를 수행합니다.

>[!IMPORTANT]
>
>Bulk Management Tools는 공식적으로 지원되는 Adobe 제품이 아닙니다. 고객 지원 센터를 통한 문제 해결 및 지원은 사안별로 처리됩니다.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC 그룹 권한](../../features/administration/administration-overview.md) 에 할당됨 [!DNL Audience Manager] UI는 [!UICONTROL Bulk Management Tools].

대량 업데이트를 수행하려면 [!UICONTROL Bulk Management Tools] 워크시트 및:

1. 다음을 클릭합니다. **[!UICONTROL Headers]** 편집할 항목의 업데이트 헤더를 탭하고 복사합니다.
2. 다음을 클릭합니다. **[!UICONTROL Update]** 탭.
3. 업데이트 워크시트의 첫 번째 행에 업데이트 헤더를 붙여 넣습니다. 다음을 참고하십시오.

   * 폴더를 업데이트할 때 모든 헤더가 필요합니다.
   * 세그먼트나 트레이트를 업데이트할 때에는 세그먼트 ID(SID)와 변경해야 하는 헤더 요소만 있으면 됩니다. 사용하지 않는 헤더를 삭제합니다.

4. 변경할 데이터를 헤더 레이블을 기반으로 해당 열에 붙여넣거나 입력합니다.
5. 워크시트 도구 모음에서 갱신 중인 항목과 일치하는 갱신 버튼을 클릭합니다.
이 작업을 수행하면 [!UICONTROL Account Information] 대화 상자.

6. 필요한 을 입력합니다. [로그온 정보](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 및 클릭 **[!UICONTROL Submit]**.

   워크시트에서 [!UICONTROL Results] 열. 다음 [!UICONTROL Results] 열은 성공적인 작업에 대한 JSON 응답을 반환합니다. 다음을 참조하십시오. [REST API](../../api/rest-api-main/rest-api-main.md) 예. 데이터를 입력하기 전에 벌크 업데이트 워크시트는 다음과 유사해야 합니다.

![](assets/update.png)

벌크 업데이트가 오류를 반환하거나 실패한 경우 [벌크 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md).
