---
description: 일괄 생성을 사용하면 단일 작업으로 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트 및 기타 항목을 구성할 수 있습니다. 다음 지침에 따라 벌크 만들기 요청을 수행합니다.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: 벌크 만들기
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# 벌크 만들기{#bulk-create}

일괄 생성을 사용하면 단일 작업으로 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트 및 기타 항목을 구성할 수 있습니다. 다음 지침에 따라 벌크 만들기 요청을 수행합니다.

>[!IMPORTANT]
>
>벌크 관리 도구는 공식적으로 지원되는 Adobe 제품이 아닙니다. 고객 지원 센터를 통한 문제 해결 및 지원은 사안별로 처리됩니다.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[ UI에 할당된 ](../../features/administration/administration-overview.md)RBAC 그룹 권한[!DNL Audience Manager]이(가) [!UICONTROL Bulk Management Tools]에서 허용됩니다.

>[!CAUTION]
>
>일괄 작성 요청에서 오브젝트 유형을 혼합하지 마십시오. 각 개체의 헤더는 고유하며 결합할 수 없습니다. 워크시트를 지우고 다른 항목에 대해 별도의 요청을 만듭니다.

개체를 일괄적으로 만들려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Headers]** 탭을 클릭하고 추가하려는 항목의 만들기 헤더를 복사합니다.
2. **[!UICONTROL Create]** 탭을 클릭합니다.
3. 만들기 헤더를 업데이트 워크시트의 첫 행에 붙여 넣습니다.
4. 변경할 데이터를 헤더 레이블을 기반으로 해당 열에 붙여넣거나 입력합니다.
5. 워크시트 도구 모음에서 업데이트할 항목과 일치하는 생성 단추를 클릭합니다.
이 작업은 [!UICONTROL Account Information] 대화 상자를 엽니다.
6. 필요한 [정보에 대한 로그](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)를 입력하고 **[!UICONTROL Submit]**&#x200B;을(를) 클릭합니다.

워크시트에서 [!UICONTROL Results] 열을 만듭니다. [!UICONTROL Results] 열은 성공적인 작업에 대한 JSON 응답을 반환합니다. 예제는 [REST API](../../api/rest-api-main/rest-api-main.md)를 참조하십시오. 데이터를 입력하기 전에 일괄 생성 워크시트가 다음 예제와 유사해야 합니다. 참고: 다양한 만들기 옵션이 모두 여기에 표시되지 않습니다. 완료된 워크시트의 모습을 이해하는 데 도움이 되도록 포함되어 있습니다.

![](assets/cretetraits.png)

벌크 업데이트가 오류를 반환하거나 실패한 경우 [대량 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하세요.
