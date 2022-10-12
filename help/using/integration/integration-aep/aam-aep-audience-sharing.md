---
description: 데이터 공유를 가능하게 하는 방법과 Audience Manager과 Adobe Experience Platform 간에 대상을 공유하는 방법을 알아봅니다
solution: Audience Manager
title: Audience Manager 및 기타 Experience Cloud 솔루션과의 Experience Platform 세그먼트 공유
keywords: AEP 대상 공유, AEP 세그먼트, 플랫폼 세그먼트, 세그먼트 공유, 대상 공유, 세그먼트 공유, AAM AEP 세그먼트 공유
feature: Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 14e0ddd00d3a25674090ea9dbe485c77ad1d2aed
workflow-type: tm+mt
source-wordcount: '1862'
ht-degree: 1%

---

# Audience Manager 및 기타 Experience Cloud 솔루션과의 Experience Platform 세그먼트 공유

## 개요 {#overview}

Audience Manager과 Adobe Experience Platform 간의 대상 공유 기능을 사용하면 Audience Manager 트레이트와 세그먼트를 Adobe Experience Platform에 공유하거나 그 반대로 공유할 수 있습니다. 다음을 수행해야 합니다. [[!DNL Audience Manager Connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) Audience Manager과 Adobe Experience Platform 간 대상 공유를 가능하게 하기 위해 .

Experience Platform의 Audience Manager 트레이트 및 세그먼트를 사용하여 고객 프로필에 Audience Manager 데이터를 추가하고 Experience Platform을 활용할 수 있습니다 [세분화 서비스](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).

Audience Manager에서 다음과 같은 데이터 관리 플랫폼 사용 사례에 Experience Platform 세그먼트를 사용할 수 있습니다.
* 추가 [타사 데이터](/help/using/overview/data-types-collected.md#third-party-data) 세그먼트를 보거나 편집하거나 삭제할 수 있습니다.
* [알고리즘 모델링](/help/using/features/algorithmic-models/understanding-models.md);
* Experience Platform에서 아직 지원되지 않는 대상으로 세그먼트를 활성화합니다 [대상 카탈로그](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

또한 Experience Platform 세그먼트는 를 통해 다른 Experience Cloud 솔루션에 공유됩니다 [핵심 서비스](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * 위에 언급된 데이터 관리 플랫폼 사용 사례를 활성화하려면 Audience Manager 라이센스가 필요합니다.
> * 사용자 *필요 없음* 핵심 서비스 통합을 통해 Adobe Advertising Cloud, Adobe Target, Marketo 및 기타 Experience Cloud 솔루션과 Experience Platform 세그먼트를 공유할 수 있는 Audience Manager 라이선스.


대상 공유 사용 사례에 대한 개요를 알려면 아래 표를 참조하십시오.

| **사용 사례** | **Adobe Experience Platform** | **Audience Manager** | **핵심 서비스** |
|---------|----------|---------|---------|
| **대상 공유** | <ul><li>Audience Manager 데이터로 고객 프로필 보강</li><li>Experience Platform 세그먼테이션에서 Audience Manager 데이터 사용</li></ul> | <ul><li>세그먼트에 타사 데이터 추가</li><li>알고리즘 모델링</li><li>추가 대상에 활성화</li></ul> | Adobe Target, Advertising Cloud 또는 Marketo과 같은 다른 Experience Cloud 솔루션에서 Experience Platform 세그먼트를 사용합니다. |

{style=&quot;table-layout:auto&quot;}

## 시작하기 - Audience Manager과 Experience Platform 간 데이터 공유를 활성화하는 방법 {#enable-data-sharing-aam-aep}

아래 두 섹션에서는 Audience Manager과 Experience Platform 간에 데이터 공유를 활성화하는 방법을 설명합니다.

### Audience Manager에서 Experience Platform으로 데이터 공유 활성화 {#enable-aam-to-aep-data}

세그먼트와 트레이트를 Audience Manager에서 Experience Platform으로 보내려면 Experience Platform 소스 카탈로그에서 Audience Manager 소스 커넥터를 설정해야 합니다. Adobe 고객 지원 또는 엔지니어링 팀의 참여가 필요하지 않은 셀프 서비스 워크플로우입니다. Audience Manager 소스 커넥터를 설정하려면 다음을 참조하십시오.

* [Audience Manager 소스](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [UI에서 Adobe Audience Manager 소스 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe은 고객이 **[!UICONTROL Select all segments]** 및 **[!UICONTROL Select all traits]** 선택 사항 을 참조하십시오. 크기 조정 가능한 Audience Manager 세그먼트 모집단을 수집하면 Audience Manager 소스를 사용하여 처음 Audience Manager 세그먼트를 Platform으로 보낼 때 총 프로필 수에 직접적인 영향을 줍니다. 즉, 모든 세그먼트를 선택하면 라이센스 사용 권한을 초과하는 프로필 수가 발생할 수 있습니다.
>
>![Audience Manager 소스 커넥터에 연결하기 위해 워크플로우에서 모든 세그먼트 선택 및 모든 트레이트 선택 선택 옵션을 선택하지 않은 상태로 표시하는 스크린샷입니다.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Experience Platform에서 Audience Manager으로 데이터 공유 활성화 {#enable-aep-to-aam-data}

>[!NOTE]
>
> 이 기능에 대한 액세스 권한을 잠금 해제하려면 Adobe 고객 성공 관리자 또는 고객 지원 팀에 문의하십시오.

세그먼트를 Experience Platform에서 Audience Manager으로 보내려면 고객 지원 센터 또는 고객 성공 관리자에게 문의해야 합니다. 고객 지원 및 고객 지원 관리 팀은 플랫폼에서 Audience Manager으로 연결을 활성화하려면 티켓을 파일(템플릿 티켓 AAM-52354 참조)해야 합니다.

Platform에서 Audience Manager으로 전송되는 데이터에 대한 계획을 공유하여 연결이 올바르게 설정되었는지 확인하십시오. 예를 들어 Adobe Target으로 전송된 세그먼트에 대해 지역 데이터를 공유해야 하는 경우 이 정보를 티켓에서 전달해야 합니다. Experience Platform에서 Audience Manager으로 데이터 공유 연결은 제출되는 요청 후 6영업일 이내에 설정됩니다.

## Adobe Experience Platform에서 세그먼트 및 트레이트 Audience Manager {#aam-segments-traits-in-aep}

Audience Manager 소스 커넥터를 설정하여 Audience Manager에서 트레이트와 세그먼트를 가져온 후 Audience Manager 데이터가 다음과 같이 Experience Platform에 표시됩니다. **대상** 세그먼트 워크플로우에서 사용할 수 있습니다. Experience Platform의 Audience Manager 세그먼트 및 트레이트에 대한 자세한 내용은 다음을 참조하십시오.

* [세그먼테이션 서비스 개요](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Experience Platform 세그먼트 빌더 사용 안내서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Audience Manager의 Adobe Experience Platform 세그먼트 {#aep-segments-in-aam}

Experience Platform에서 만든 세그먼트는 다음 구성 규칙을 사용하여 Audience Manager 인터페이스에 신호, 트레이트 및 세그먼트로 표시됩니다.

* 신호: 각 Experience Platform 세그먼트에 대해 양식에 신호가 표시됩니다 `segID = segment ID`.
* 트레이트: 트레이트 규칙은 Experience Platform 세그먼트의 ID입니다.
* 세그먼트: 세그먼트는 위에 설명된 트레이트로 구성됩니다.

### 신호 {#aep-segments-as-aam-signals}

선택 **[!UICONTROL Audience Data > Signals > General Online Data]** 검색 기준 `SegId` Experience Platform에서 들어오는 신호를 찾습니다. 디버깅을 위해 이 화면을 사용하여 Experience Platform과 Audience Manager 간 통합이 올바르게 설정되었는지 확인할 수 있습니다.

![신호 대시보드의 Audience Manager에서 Experience Platform 신호 을 참조하십시오](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 트레이트 {#aep-segments-as-aam-traits}

Audience Manager은 **Experience Platform 트레이트** 트레이트 저장소에서 다음을 수행합니다.

![Experience Platform 대시보드의 트레이트](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

세그먼트에서 다른 트레이트와 함께 자동으로 생성된 트레이트를 사용할 수 있습니다. 예를 들어 Experience Platform 세그먼트에서 생성된 트레이트를 를 [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Experience Platform 세그먼트에서 자동으로 생성된 트레이트의 예는 아래 스크린샷을 참조하십시오.

![Experience Platform의 트레이트](/help/using/integration/integration-aep/assets/aep-trait.png)


| 항목 번호 | 이름 | 설명 |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Experience Platform 세그먼트에서 생성된 트레이트는 Audience Manager에서 온보딩된 트레이트로 만들어집니다. |
| 2 | [!UICONTROL Data Source] | 자동으로 만들어집니다. Experience Platform 세그먼트에서 자동으로 만들어지는 모든 트레이트와 세그먼트는 데이터 소스에 저장됩니다 **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | 통합 코드는 Experience Platform의 세그먼트 ID에 해당합니다. |
| 4 | [!UICONTROL Trait Expression] | 트레이트 표현식은 다음과 같습니다 `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | 이 트레이트를 컴포지션으로 사용하는 자동으로 생성된 세그먼트입니다. |

{style=&quot;table-layout:auto&quot;}

### 세그먼트 {#aep-segments-as-aam-segments}

Audience Manager은 **Experience Platform 세그먼트** 세그먼트 저장소 내.

![대시보드 스크린샷](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Experience Platform 세그먼트에서 자동으로 생성된 세그먼트의 예는 아래 스크린샷을 참조하십시오.

![세그먼트의 스크린샷](/help/using/integration/integration-aep/assets/aep-segment.png)

| 항목 번호 | 이름 | 설명 |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | 통합 코드는 Experience Platform의 세그먼트 ID에 해당합니다. |
| 2개 | [!UICONTROL Data Source] | 자동으로 만들어집니다. Experience Platform 세그먼트에서 자동으로 만들어지는 모든 트레이트와 세그먼트는 데이터 소스에 저장됩니다 **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** 자동으로 생성된 세그먼트가 Experience Platform에서 설정된 병합 정책을 따르도록 지정합니다. |
| 4 | [!UICONTROL Segment Rule] | 세그먼트는 다음에 설명된 트레이트로 구성됩니다 [트레이트 섹션](#aep-segments-as-aam-traits). |

{style=&quot;table-layout:auto&quot;}

## Experience Platform에서 Audience Manager 데이터 내보내기 제어 지원 {#aam-data-export-control-in-aep}

Experience Platform에서 데이터 사용 규정을 준수하려면 적용 가능한 모든 데이터 세트 및 필드를 적절하게 지정해야 합니다 [데이터 사용 레이블](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html). 게다가, [데이터 사용 정책](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html) 는 [DULE(Data Usage Labeling and Enforcement) 프레임워크](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework).

Audience Manager과 Experience Platform 간의 대상 공유 프로세스에서 Audience Manager 세그먼트에 적용된 모든 데이터 내보내기 컨트롤은 Experience Platform 데이터 거버넌스에서 인식하는 동등한 레이블 및 마케팅 작업으로 변환되며, 그 반대의 경우도 마찬가지입니다.

>[!NOTE]
>
>데이터 내보내기 컨트롤에 대한 자세한 내용은 [데이터 내보내기 제어 설명서](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>이 문서에서는 특정 Audience Manager 데이터 내보내기 컨트롤이 Platform의 데이터 사용 레이블 및 마케팅 작업에 매핑되는 방식에 대한 참조를 제공합니다.

### 데이터 내보내기 컨트롤을 데이터 사용 레이블로 내보내기

다음 표에서는 특정 데이터 내보내기 컨트롤이 인식된 데이터 사용 레이블에 매핑되는 방식을 설명합니다.

| 데이터 내보내기 제어 | 데이터 사용 레이블 |
| --- | --- |
| 개인 식별 정보에는 사용할 수 없습니다 | C3: 데이터는 결합하거나 직접 식별 가능한 정보와 함께 사용할 수 없습니다 |
| 오프사이트 광고 타깃팅에는 사용할 수 없습니다. | C5: 데이터는 컨텐츠 또는 광고에 대한 관심사 기반의 사이트 간 타깃팅에 사용할 수 없습니다 |
| 온사이트 광고 타깃팅에 사용할 수 없습니다. | C6: 온사이트 광고 타깃팅에는 데이터를 사용할 수 없습니다 |
| 온사이트 개인화에 사용할 수 없음 | C7: 데이터는 컨텐츠를 온사이트 타깃팅하는 데 사용할 수 없습니다 |

{style=&quot;table-layout:auto&quot;}

### 마케팅 작업으로 데이터 내보내기 제어

다음 표는 특정 데이터 내보내기 레이블이 인식된 마케팅 작업에 매핑되는 방식을 설명합니다.

| 데이터 내보내기 레이블 | 마케팅 작업 |
| --- | --- |
| 이 대상은 PII(개인 식별 정보)와 함께 사용할 수 있습니다 | PII와 결합 |
| 이 대상은 오프사이트 광고 타깃팅에 사용할 수 있습니다 | 사이트 간 타깃팅 |
| 이 대상은 온사이트 광고 타깃팅에 사용할 수 있습니다 | 온사이트 광고 |
| 이 대상은 온사이트 광고 개인화에 사용할 수 있습니다 | 온사이트 개인화 |

{style=&quot;table-layout:auto&quot;}

## Audience Manager과 Experience Platform 간의 세그먼트 모집단 차이 이해 {#aep-aam-segment-population-differences}

Audience Manager 모집단 번호는 세그먼트와 Experience Platform 세그먼트 간에 다를 수 있습니다. 유사하거나 동일한 대상의 세그먼트 번호는 비슷해야 하지만, 모집단의 차이는 아래에 나열된 요소로 인해 발생할 수 있습니다.

### Experience Platform의 세그먼트 평가

Audience Manager은 인터페이스에서 하루에 한 번 보고 번호를 업데이트합니다. 이 업데이트 시점은 Experience Platform에서 세그먼트 평가 시간에 거의 맞지 않습니다.

### 프로필 병합 규칙과 병합 정책 간의 차이점

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) Audience Manager 및 [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) Experience Platform에서 다르게 작동하며 각각에 사용되는 id 그래프가 달라집니다. 이로 인해 세그먼트 모집단 간의 몇 가지 차이점이 예상됩니다.

>[!NOTE]
>
> Experience Platform에서 Audience Manager으로 세그먼트를 공유할 때 플랫폼 조직 [기본 병합 정책](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) 는 보다 우선합니다. [세그먼트에서 사용하는 병합 정책](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) 공유한 모든 세그먼트를 표시합니다. 예를 들어, 공유 세그먼트의 병합 정책이 [ID 결합](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure)그러나 조직의 기본 병합 정책은 적용되지 않습니다. 이로 인해 플랫폼과 Audience Manager 간에 모집단 차이가 발생할 수 있습니다.

### Experience Platform의 세그먼트 구성

Adobe Experience Platform과 Audience Manager 간의 통합은 많은 표준을 공유합니다 [id 네임스페이스](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) 모든 고객에 대해 다음을 수행합니다. ECID, IDFA, GAID, 해시된 이메일 주소(EMAIL_LC_SHA256), AdCloud ID. Experience Platform 세그먼트에서 자격이 있는 프로필에 대한 기본 ID로 이러한 프로필을 사용하는 경우 프로필은 Audience Manager 트레이트 및 세그먼트에서 카운트됩니다.

>[!NOTE]
>
> 원시 이메일을 키로 ID를 사용하는 Experience Platform의 대상은 Audience Manager에 표시되지 않습니다.

예를 들어 Experience Platform 세그먼트 &quot;All my customers&quot;가 있고 자격이 있는 프로필이 CRM ID, ECID, IDFA, 원시 및 해시된 이메일 주소인 경우, Audience Manager의 해당 세그먼트에는 ECID, IDFA 및 해시된 이메일 주소에서 처리된 프로필만 포함됩니다. Audience Manager의 세그먼트 모집단은 Experience Platform의 세그먼트 모집단보다 작습니다.

![세그먼트 공유에 대한 Experience Platform - 세그먼트 구성](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [세그먼테이션 서비스 개요](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform 세그먼트 빌더 사용 안내서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

