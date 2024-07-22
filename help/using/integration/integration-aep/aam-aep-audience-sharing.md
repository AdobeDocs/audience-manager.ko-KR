---
description: 데이터 공유를 활성화하는 방법 및 Audience Manager과 Adobe Experience Platform 간에 대상자를 공유하는 방법에 대해 알아봅니다
solution: Audience Manager
title: Audience Manager 및 기타 Experience Cloud 솔루션과 공유하는 Experience Platform 세그먼트
keywords: AEP 대상 공유, AEP 세그먼트, Platform 세그먼트, 세그먼트 공유, 대상 공유, 세그먼트 공유, AAM AEP 세그먼트 공유
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Audience Manager 및 기타 Experience Cloud 솔루션과 공유하는 Experience Platform 세그먼트

## 개요 {#overview}

Audience Manager과 Adobe Experience Platform 간의 대상 공유 기능을 사용하면 Audience Manager 트레이트 및 세그먼트를 Adobe Experience Platform에 공유하고 세그먼트를 Experience PlatformAudience Manager 에 공유할 수 있습니다.

Audience Manager과 Adobe Experience Platform 간에 대상을 공유하려면 Experience Platform에 [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) 및 [Experience Cloud 대상](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) 대상이 필요합니다.

Experience Platform에서 Audience Manager 트레이트 및 세그먼트를 사용하여 고객 프로필에 Audience Manager 데이터를 추가하고 Experience Platform [세그먼테이션 서비스](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en)의 혜택을 받을 수 있습니다.

Audience Manager에서 다음과 같은 데이터 관리 플랫폼 사용 사례에 Experience Platform 세그먼트를 사용할 수 있습니다.
* 세그먼트에 [타사 데이터](/help/using/overview/data-types-collected.md#third-party-data) 추가;
* [알고리즘 모델링](/help/using/features/algorithmic-models/understanding-models.md);
* Experience Platform [대상 카탈로그](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)에서 아직 지원되지 않는 대상에 대한 세그먼트를 활성화합니다.

또한 Experience Platform 세그먼트는 [핵심 서비스](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html)를 통해 다른 Experience Cloud 솔루션에 공유됩니다.

>[!IMPORTANT]
>
> * 위에서 언급한 데이터 관리 플랫폼 사용 사례를 활성화하려면 Audience Manager 라이선스가 필요합니다.
> * 핵심 서비스 통합을 통해 Adobe Advertising Cloud, Adobe Target, Marketo 및 기타 Experience Cloud 솔루션과 Experience Platform 세그먼트를 공유하는 데 Audience Manager 라이선스가 *필요하지 않습니다*.

대상 공유 사용 사례에 대한 개요는 아래 표를 참조하십시오.

| **사용 사례** | **Adobe Experience Platform** | **Audience Manager** | **핵심 서비스** |
|---------|----------|---------|---------|
| **대상 공유** | <ul><li>Audience Manager 데이터를 사용하여 고객 프로필 강화</li><li>Experience Platform 세분화에서 Audience Manager 데이터 사용</li></ul> | <ul><li>세그먼트에 타사 데이터 추가</li><li>알고리즘 모델링</li><li>추가 대상에 대한 활성화</li></ul> | Adobe Target, Advertising Cloud 또는 Marketo과 같은 다른 Experience Cloud 솔루션에서 Experience Platform 세그먼트를 사용합니다. |

{style="table-layout:auto"}

## Adobe Experience Platform에서 세그먼트 및 트레이트 Audience Manager {#aam-segments-traits-in-aep}

아래 섹션에서는 Audience Manager에서 Experience Platform으로 데이터 공유를 활성화하는 방법과 Experience Platform에서 Audience Manager 트레이트 및 세그먼트를 사용하는 방법에 대해 설명합니다.

### Audience Manager에서 Experience Platform으로 데이터 공유 활성화 {#enable-aam-to-aep-data}

세그먼트와 트레이트를 Audience Manager에서 Experience Platform으로 보내려면 Experience Platform 소스 카탈로그에서 Audience Manager 소스 커넥터를 설정해야 합니다. Adobe 고객 지원 센터 또는 엔지니어링 팀의 관여가 필요 없는 셀프서비스 워크플로우입니다. Audience Manager 소스 커넥터를 설정하려면 다음을 참조하십시오.

* [Audience Manager 원본](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [UI에서 Adobe Audience Manager 소스 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe은 아래와 같이 **[!UICONTROL Select all segments]** 및 **[!UICONTROL Select all traits]** 옵션을 선택하지 않고 연결을 구성하도록 고객을 권장합니다. 크기 조정 가능한 Audience Manager 세그먼트 모집단의 수집은 Audience Manager 소스를 사용하여 Audience Manager 세그먼트를 처음 플랫폼으로 보낼 때 총 프로필 수에 직접적인 영향을 미칩니다. 즉, 모든 세그먼트를 선택하면 라이선스 사용 권한을 초과하는 프로필 수가 발생할 수 있습니다.
>
>![Audience Manager 원본 커넥터에 연결할 워크플로에서 모든 세그먼트 선택 및 모든 트레이트 선택 옵션을 선택 취소한 스크린샷을 보여 줍니다.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Experience Platform에서 Audience Manager 트레이트 및 세그먼트 사용 {#use-aam-data-in-aep}

Audience Manager에서 트레이트 및 세그먼트를 가져오도록 Audience Manager 소스 커넥터를 설정한 후에는 Audience Manager 데이터가 Experience Platform 워크플로에서 **대상**(으)로 세그먼트에 표시됩니다. Experience Platform의 Audience Manager 세그먼트 및 트레이트에 대한 자세한 내용은 다음을 참조하십시오.

* [세그먼테이션 서비스 개요](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Experience Platform 세그먼트 빌더 사용 안내서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Audience Manager의 Adobe Experience Platform 세그먼트 {#aep-segments-in-aam}

아래 섹션에서는 Experience Platform에서 Audience Manager으로 데이터 공유를 활성화하는 방법과 Audience Manager에서 Experience Platform 세그먼트를 사용하는 방법에 대해 설명합니다.

### Experience Platform에서 Audience Manager으로 데이터 공유 활성화 {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> 이 섹션에서는 Experience Platform에서 Audience Manager으로 기존 세그먼트 공유 통합에 대해 설명합니다. 이제 Adobe 고객 담당자의 지원 없이 이 통합을 설정할 수 있습니다. 자세한 내용은 [Experience Cloud 대상](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) 대상 설명서를 참조하십시오.

>[!NOTE]
>
> 이 기능에 대한 액세스 권한을 잠금 해제하려면 Adobe 고객 성공 관리자 또는 고객 지원 센터에 문의하십시오.

세그먼트를 Experience Platform에서 Audience Manager으로 보내려면 고객 지원 센터 또는 고객 성공 관리자에게 문의해야 합니다. 고객 지원 센터 및 고객 지원 관리 팀이 플랫폼에서 Audience Manager으로 연결하려면 티켓을 제출해야 합니다(템플릿 티켓 AAM-52354 참조).

연결이 올바로 설정되도록 플랫폼에서 Audience Manager으로 이동하는 데이터에 대한 계획을 공유해야 합니다. 예를 들어, Adobe Target으로 전송된 세그먼트에 대해 지역 데이터를 공유해야 하는 경우, 이 정보는 티켓에서 통신해야 합니다. Experience Platform에서 Audience Manager으로 데이터 공유 연결은 요청이 제출된 후 영업일 기준으로 6일 이내에 설정됩니다.

### Audience Manager에서 Experience Platform 세그먼트 사용 {#use-aep-data-in-aam}

Experience Platform에서 만드는 세그먼트는 Audience Manager 인터페이스에 다음 구성 규칙이 있는 신호, 트레이트 및 세그먼트로 표시됩니다.

* 신호: 각 Experience Platform 세그먼트에 대해 `segID = segment ID` 형식의 신호가 표시됩니다.
* 트레이트: 트레이트 규칙은 Experience Platform 세그먼트의 ID입니다.
* 세그먼트: 세그먼트는 위에서 설명한 트레이트로 구성됩니다.

### 신호 {#aep-segments-as-aam-signals}

**[!UICONTROL Audience Data > Signals > General Online Data]**&#x200B;을(를) 선택하고 `SegId`(으)로 검색하여 Experience Platform에서 들어오는 신호를 찾습니다. 이 화면을 사용하여 디버깅 목적으로 Experience Platform과 Audience Manager 간의 통합이 올바르게 설정되었는지 확인할 수 있습니다.

![신호 대시보드의 Audience Manager에서 Experience Platform 신호 보기](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 트레이트 {#aep-segments-as-aam-traits}

Audience Manager은 특성 저장소에 **Experience Platform 특성**&#x200B;이라는 특성 폴더를 자동으로 만듭니다.

![Experience Platform 대시보드의 트레이트](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

세그먼트에서 자동으로 생성된 트레이트를 다른 트레이트와 함께 사용할 수 있습니다. 예를 들어 Experience Platform 세그먼트에서 만든 트레이트를 [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)을 통해 획득한 타사 트레이트와 혼합할 수 있습니다.

Experience Platform 세그먼트에서 자동으로 생성된 트레이트의 예는 아래 스크린샷을 참조하십시오.

![Experience Platform 트레이트](/help/using/integration/integration-aep/assets/aep-trait.png)


| 항목 번호 | 이름 | 설명 |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Experience Platform 세그먼트에서 생성된 트레이트는 Audience Manager에서 온보딩된 트레이트로 만들어집니다. |
| 2 | [!UICONTROL Data Source] | 자동으로 만들어집니다. Experience Platform 세그먼트에서 자동으로 만들어진 모든 트레이트 및 세그먼트는 데이터 원본 **[!UICONTROL Adobe Experience Platform Audience Sharing]**&#x200B;에 저장됩니다. |
| 3 | [!UICONTROL Integration Code] | 통합 코드는 Experience Platform의 세그먼트 ID에 해당합니다. |
| 4 | [!UICONTROL Trait Expression] | 특성 식은 `segID = segment ID in Experience Platform`입니다. |
| 5 | [!UICONTROL Segments with this Trait] | 이 트레이트를 컴포지션으로 사용하여 자동으로 생성된 세그먼트입니다. |

{style="table-layout:auto"}

### 세그먼트 {#aep-segments-as-aam-segments}

Audience Manager은 세그먼트 저장소에 **Experience Platform 세그먼트**&#x200B;라는 세그먼트 폴더를 자동으로 만듭니다.

![대시보드의 스크린샷](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Experience Platform 세그먼트에서 자동으로 생성된 세그먼트의 예는 아래 스크린샷을 참조하십시오.

![세그먼트의 스크린샷](/help/using/integration/integration-aep/assets/aep-segment.png)

| 항목 번호 | 이름 | 설명 |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | 통합 코드는 Experience Platform의 세그먼트 ID에 해당합니다. |
| 2 | [!UICONTROL Data Source] | 자동으로 만들어집니다. Experience Platform 세그먼트에서 자동으로 만들어진 모든 트레이트 및 세그먼트는 데이터 원본 **[!DNL Adobe Experience Platform Audience Sharing]**&#x200B;에 저장됩니다. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]**&#x200B;은(는) 자동으로 만들어진 세그먼트가 Experience Platform에서 설정된 병합 정책을 따르도록 나타냅니다. |
| 4 | [!UICONTROL Segment Rule] | 세그먼트는 [트레이트 섹션](#aep-segments-as-aam-traits)에 설명된 트레이트로 구성됩니다. |

{style="table-layout:auto"}

## Experience Platform에서 Audience Manager 데이터 내보내기 제어 지원 {#aam-data-export-control-in-aep}

Experience Platform에서 데이터 사용 규정 준수를 적용하려면 적용 가능한 모든 데이터 세트와 필드에 적절한 [데이터 사용 레이블](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=ko-KR)을 지정해야 합니다. 또한 [DULE(데이터 사용 레이블 및 적용) 프레임워크](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework)에 설명된 대로 해당 레이블에 대한 특정 마케팅 작업에 대해 [데이터 사용 정책](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=ko-KR)을(를) 사용하도록 설정해야 합니다.

Audience Manager과 Experience Platform 간의 대상 공유 프로세스에서, Audience Manager 세그먼트에 적용된 모든 데이터 내보내기 컨트롤은 Experience Platform 데이터 거버넌스에서 인식하는 동등한 레이블 및 마케팅 작업으로 변환되고 그 반대의 경우도 마찬가지입니다.

>[!NOTE]
>
>데이터 내보내기 제어에 대한 일반적인 정보는 [데이터 내보내기 제어 설명서](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)를 참조하십시오.
>
>이 문서에서는 특정 Audience Manager 데이터 내보내기 제어 가 Platform의 데이터 사용 레이블 및 마케팅 작업에 매핑되는 방법에 대한 참조를 제공합니다.

### 데이터 사용 레이블에 대한 데이터 내보내기 제어

다음 표에서는 특정 데이터 내보내기 제어 기능이 인식된 데이터 사용 레이블에 매핑되는 방식을 설명합니다.

| 데이터 내보내기 제어 | 데이터 사용 레이블 |
| --- | --- |
| 개인 식별 정보와 함께 사용할 수 없음 | C3: 데이터는 직접 식별 가능한 정보와 결합하거나 사용할 수 없습니다. |
| 오프사이트 광고 타깃팅에는 사용할 수 없음 | C5: 콘텐츠 또는 광고의 관심 기반 크로스 사이트 타겟팅에는 데이터를 사용할 수 없습니다 |
| 온사이트 광고 타깃팅에는 사용할 수 없음 | C6: 온사이트 광고 타깃팅에는 데이터를 사용할 수 없음 |
| 온사이트 개인화에 사용할 수 없음 | C7: 온사이트 콘텐츠 타겟팅에는 데이터를 사용할 수 없음 |

{style="table-layout:auto"}

### 마케팅 액션으로 데이터 내보내기 제어

다음 표에서는 특정 데이터 내보내기 레이블이 인식된 마케팅 작업에 매핑되는 방식을 설명합니다.

| 데이터 내보내기 레이블 | 마케팅 액션 |
| --- | --- |
| 이 대상은 PII(개인 식별 정보)와의 조합을 활성화할 수 있습니다 | PII와 결합 |
| 이 대상은 오프사이트 광고 타겟팅에 사용할 수 있습니다. | 크로스 사이트 타겟팅 |
| 이 대상은 온사이트 광고 타겟팅에 사용할 수 있습니다. | 온사이트 Advertising |
| 이 대상은 온사이트 및 개인화에 사용할 수 있습니다. | 온사이트 Personalization |

{style="table-layout:auto"}

## Audience Manager과 Experience Platform 간의 세그먼트 모집단 차이점 이해 {#aep-aam-segment-population-differences}

세그먼트 모집단 번호는 Audience Manager과 Experience Platform 세그먼트 간에 다를 수 있습니다. 유사하거나 동일한 대상에 대한 세그먼트 번호는 근접해야 하지만, 모집단의 차이는 아래 나열된 요소 때문일 수 있습니다.

### Experience Platform의 세그먼트 평가

Audience Manager은 하루에 한 번 인터페이스의 보고 번호를 업데이트합니다. 이 업데이트의 타이밍이 Experience Platform의 세그먼트 평가 시간과 일치하는 경우는 거의 없습니다.

### 프로필 병합 규칙과 병합 정책 간의 차이점

Audience Manager의 [[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md)과(와) Experience Platform의 [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html)은(는) 다르게 작동하며 각각에 사용되는 id 그래프가 다릅니다. 이로 인해 세그먼트 모집단 간의 일부 차이가 예상됩니다.

>[!NOTE]
>
> Experience Platform에서 Audience Manager으로 세그먼트를 공유할 때 플랫폼 조직 [기본 병합 정책](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy)이(가) Audience Manager과 공유된 ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) 세그먼트에서 사용하는 [병합 정책보다 우선합니다. 예를 들어 공유 세그먼트의 병합 정책에서 [ID 결합](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure)을 허용하지만 조직의 기본 병합 정책이 허용하지 않는 경우, 플랫폼과 Audience Manager 간에 모집단 차이가 발생할 수 있습니다.

### Experience Platform의 세그먼트 구성

Adobe Experience Platform과 Audience Manager 간의 통합은 모든 고객을 위해 ECID, IDFA, GAID, 해시된 이메일 주소(EMAIL_LC_SHA256), AdCloud ID와 같은 많은 표준 [ID 네임스페이스](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types)를 공유합니다. Experience Platform 세그먼트가 이들 중 하나를 적격 프로필에 대한 기본 ID로 사용하는 경우 프로필은 Audience Manager 트레이트 및 세그먼트에서 계산됩니다.

>[!NOTE]
>
> 원시 이메일에 입력된 ID가 있는 Experience Platform의 대상은 Audience Manager에 표시되지 않습니다.

예를 들어 Experience Platform 세그먼트 &quot;모든 내 고객&quot;이 있고 자격 있는 프로필이 CRM ID, ECID, IDFA, 원시 및 해시된 이메일 주소인 경우, Audience Manager의 해당 세그먼트에는 ECID, IDFA 및 해시된 이메일 주소에서 처리된 프로필만 포함됩니다. Audience Manager의 세그먼트 모집단은 Experience Platform의 세그먼트 모집단보다 작습니다.

![Audience Manager 세그먼트 공유 Experience Platform - 세그먼트 구성](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [세그먼테이션 서비스 개요](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform 세그먼트 빌더 사용 안내서](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
