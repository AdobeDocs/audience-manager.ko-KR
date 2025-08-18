---
description: 사용자 기반 대상에 대한 일반적인 질문에 대한 답변입니다.
seo-description: Answers to common questions about People-Based Destinations.
seo-title: People-Based Destinations FAQ
solution: Audience Manager
title: 사용자 기반 대상 FAQ
feature: People-based Destinations
exl-id: 56506bf0-45f1-49df-81ac-10f57a2487eb
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 93%

---

# 사용자 기반 대상 FAQ {#people-based-destinations-faq}

[!DNL People-Based Destinations]에 대한 일반적인 질문에 대한 답변입니다.

## 가용성 {#availability}

**Audience Manager 계정 [!DNL People-Based Destinations]을 볼 수 없습니다. 가용성에 대해 무엇을 알아야 합니까?**

[!DNL People-Based Destinations]은 구입 시 사용할 수 있는 프리미엄 Audience Manager 기능입니다. 가격 및 가용성에 대한 자세한 내용은 Adobe 영업 담당자에게 문의하십시오.

## 데이터 온보딩 {#data-onboarding}

**[!DNL People-Based Destinations]에서 사용할 수 있도록 고객 이메일 주소를 Audience Manager에 온보딩하려면 어떻게 해야 합니까?**

[!DNL People-Based Destinations]용으로 오프라인 데이터를 Audience Manager에 가져올 수 있는 방법에는 두 가지가 있습니다.

* **파일 기반 ID 동기화를 사용**&#x200B;하십시오. ID 동기화 파일의 모습에 대한 자세한 내용은 [ID 동기화 파일 이름 및 컨텐츠 요구 사항](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)을 참조하십시오. 이 방법을 사용하는 경우 [!DNL CRM] 데이터베이스에서 해시된 모든 이메일 주소를 타겟팅할 수 있습니다.
* 인증된 고객 ID를 전달할 때 **선언된 ID를 사용**&#x200B;하여 해시된 이메일 주소를 선언하십시오. 이 방법을 사용하는 경우 Audience Manager는 온라인에서 인증된 사용자의 해시된 이메일 주소만 활성화합니다. Facebook을 통해 활성화된 이메일 주소는 선언된 ID 이벤트 호출에 있는 이메일 주소만 해당됩니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 활성화되지 않습니다.

**해시된 이메일 주소를 웹 양식이나 모바일 앱을 통해 수집할 수 있습니까, 아니면 배치 파일을 통해 받아야 합니까?**

[선언된 ID](../features/declared-ids.md)와 함께 [!DNL ECID]를 사용하여 웹 인증을 통해 해시된 이메일 주소를 수집할 수 있습니다. 또한 배치 파일을 사용하면 인증을 통해 보낼 수 없는 해시된 이메일 주소(예: [!DNL CRM]에 있는 휴면 상태 사용자)를 수집하여 사용자 기반 대상에서 활성화할 수 있습니다.

**웹 양식을 통해 해시된 이메일 주소를 섭취하는 것은 배치 파일을 통해 해시된 이메일 주소를 업로드하는 것과 어떻게 다릅니까?**

오프라인 데이터 섭취는 인증 없이 사용 사례를 지원하기 위해 고안되었으며, 인증과 관계없이 모든 오프라인 [!UICONTROL All Cross-Device Profiles] 프로필에서 실행되는 새로운 프로필 병합 규칙([!DNL CRM])은 [!DNL People-Based Destinations]의 일부로 사용할 수 있습니다. 이 방법은 온라인 소스에서 인증된 대상자를 수집하는 것을 보완하기 위한 것입니다.

**해시된 이메일 주소를 전송/업데이트할 수 있는 최대 빈도는 얼마입니까?**

* 선언된 ID를 사용할 때 Audience Manager는 해시된 이메일 주소를 대상에 실시간으로 보냅니다.
* ID 동기화 파일을 통해 데이터를 섭취할 때 Audience Manager는 일일 단위로 데이터를 처리합니다.

**이메일 주소 해싱이 올바로 수행되었는지 어떻게 알 수 있습니까?**

Audience Manager는 원시 이메일 주소를 섭취하는 것이 아니므로 해시가 올바로 수행되었는지는 확인할 수 없습니다. 온보딩된 데이터를 해시할 때 사용해야 하는 방법에 대한 자세한 내용은 [사전 요구 사항 및 고려 사항](../features/destinations/people-based-destinations-prerequisites.md)을 참조하십시오.

## 프로필 병합 규칙 {#profile-merge-rules}

**[!DNL People-Based Destinations]과 함께 사용할 수 있는 새 프로필 병합 규칙이 있습니까?**

예. [!DNL People-Based Destinations]을 구입하는 고객은 오프라인 세그먼테이션을 위해 새 프로필 병합 규칙에 대한 액세스 권한도 부여받습니다. 이 규칙은 [!DNL All Cross-Device Profiles]이라고 하며 오프라인 전용 세그먼테이션에 사용됩니다. [!DNL People-Based Destinations]에 등록할 때 기존 인증 기반 규칙 3개를 제외하고 만들 수 있는 네 번째 프로필 병합 규칙입니다.

**[!DNL People-Based Destinations]에서 기존 대상자 세그먼트를 활성화하려면 복제해야 합니까?**

사용 사례에 따라 다릅니다. 사용자 기반 채널에서 기존 자사 세그먼트를 활성화할 계획이라면 새 세그먼트를 만들 필요가 없습니다. 세그먼트를 사용자 기반 대상에 매핑할 수 있습니다.

사용자 기반 채널에서 새 오프라인 대상자를 활성화할 계획이라면 [!DNL All Cross-Device Profiles] 병합 규칙을 사용하여 새 자사 세그먼트를 만들어야 합니다.
>[!NOTE]
>
> 자사 데이터가 있는 세그먼트만 [!DNL People-Based Destinations]에 매핑할 수 있습니다. Adobe의 대상 플랫폼은 제2자 데이터와 타사 데이터가 있는 세그먼트를 허용하지 않습니다.

## 일치율 {#match-rates}

**[!DNL People-Based Destinations]는 일치율 또는 대응 가능 대상자를 표시할 수 있습니까?**

아니요. 대상자 세그먼트를 [!DNL People-Based Destinations]에 보낼 때 파트너 측에서는 대상자 일치가 발생합니다. Adobe는 해당 지표에 액세스할 수 없습니다. Audience Manager는 각 대상에 대한 공유 가능한 최대 대상 및 세그먼트에 속하는 사람들의 실시간 수를 보여 줍니다. 이 정보는 캠페인 계획 및 예측에 도움이 될 수 있습니다.

**[!DNL People-Based Destinations]를 사용하는 일치율은 고객을 대상 플랫폼에 보내는 다른 방법과 어떻게 이론적으로 비교됩니까?**

이메일 주소가 올바로 해시되고 섭취되는 한 [!DNL People-Based Destinations]와 다른 방법 간 일치율에 차이가 없어야 합니다. 일치율이 100% 미만이 되는 유일한 이유는 Audience Manager에 가져온 이메일 주소가 대상 플랫폼의 사용자 기반에 있는 이메일 주소와 일치시킬 수 없는 경우입니다.

**제 고객으로부터 소셜 네트워크에 사용되는 개인 이메일 주소와 다른 회사 이메일 주소를 수집하고 있습니다. 여러 이메일 주소에서 ID를 일치시키려면 어떻게 합니까?**

Audience Manager는 사용자당 최대 10개의 이메일을 수집하여 대상 플랫폼에 보낼 수 있지만 이메일 주소는 동기화 파일을 통해 캡처해야 합니다. Audience Manager가 대상 플랫폼에 이메일 주소를 보낸 후 이메일 주소를 자체 사용자 기반에 대해 일치시키는 것은 플랫폼에 달려 있습니다. 일부 플랫폼에는 Audience Manager에서 사용자 프로필에 보낸 주소를 일치시키기 위한 추가적인 이메일 주소 그래프가 있을 수 있습니다.

**[!DNL People-Based Destinations]에서 [!DNL Audience Lab]을(를) 사용할 수 있습니까?**

아니요. 현재 모든 [!DNL People-Based Destinations] 대상이 [!DNL Audience Lab]에서 제외되어 있습니다. [!DNL People-Based Destinations]과(와) 수요 측 플랫폼에서 서로 다른 ID를 사용하므로 대상을 균등하게 분할하여 성능을 테스트하고 측정할 수 없습니다.

## 데이터 내보내기 제어 {#data-export-controls}

**[!DNL Data Export Controls]은 [!DNL People-Based Destinations]에서 어떻게 작동합니까?**

[!DNL Data Export Controls]는 사용자가 [!DNL People-Based Destinations]에 보내려 하는 제2자 데이터와 타사 데이터가 포함된 모든 세그먼트를 차단합니다. [!DNL People-Based Destinations]에서는 타겟팅에 자사 데이터만 사용할 수 있습니다. 또한 [!DNL Data Export Controls]는 장치 그래프와 함께 [!DNL Profile Merge Rules]을 사용하여 세그먼트를 차단합니다. [!DNL People-Based Destinations]은 적절한 데이터 내보내기 레이블이 선택된 상태로 만들어지는데 내보내기 설정은 덮어쓸 수 없습니다.

## 파트너 관련 질문 {#partner-specific-questions}

### [!DNL Facebook]

**대상자 세그먼트를 [!DNL Facebook]에 보낼 수 있으려면 먼저 무엇을 해야 합니까?**

[!DNL People-Based Destinations]을 사용하여 대상자 세그먼트를 [!DNL Facebook]에 보내려면 먼저 다음 구성 작업을 수행해야 합니다.

1. [!DNL Facebook Ad Account]에서 광고 파트너로서 Adobe Experience Cloud 비즈니스 계정을 추가합니다. `business ID=206617933627973`를 사용하십시오. 자세한 내용은 비즈니스 관리자에 파트너 추가를 참조하십시오.

   >[!IMPORTANT]
   >
   > Adobe Experience Cloud에 대한 권한을 구성할 때 캠페인 관리 권한을 활성화해야 합니다. 이 단계는 [!DNL People-Based Destinations] 통합에 필요합니다.

1. [!DNL Facebook Custom Audiences Terms of Service]을 읽고 서명합니다. 이렇게 하려면 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`로 이동하십시오. 여기서 `accountID`는 [!DNL Facebook Ad Account ID]입니다.

**[!DNL People-Based Destinations]은 [!DNL Instagram]과 같은 다른 [!DNL Facebook] 앱에서 대상자 타기팅을 지원합니까?**

[!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] 및 [!DNL Messenger]을 포함하여 [!DNL Custom Audiences]이 지원하는 [!DNL Facebook]의 앱 제품군에서 [!DNL People-Based Destinations]을 사용할 수 있습니다. 캠페인을 실행할 앱의 선택은 [!DNL Facebook Ads Manager]의 배치 수준에서 표시됩니다.

**[!DNL People-Based Destinations]과 [!DNL Website Custom Audiences] 간의 차이점은 무엇입니까?**

[!DNL People-Based Destinations]은 [!DNL Facebook]과의 [!DNL Custom Audiences (CA)] 통합을 활용합니다. [!DNL WCA]와 [!DNL CA] 통합의 차이점은 고객이 [!DNL Facebook]에 대상자를 보낼 때 사용하는 키입니다. [!DNL WCA]는 [!DNL Facebook] 픽셀(웹 사이트 사용자 ID임)을 사용하고 [!DNL People-Based Destinations]은 해시된 이메일 주소를 사용하여 [!DNL CA]와 통합합니다.

추가 비용없이 [!DNL URL Destinations] 기능을 통해 Audience Manager의 [!DNL Facebook] [!DNL WCA] 통합을 사용할 수 있습니다.

이 두 가지 통합은 상호 보완적입니다. 두 가지 모두를 사용하여 대상자 범위를 개선할 수 있습니다. 예를 들어, [!DNL WCA]는 회사가 계정을 등록하지 않은 웹 사이트 방문자를 타겟팅하려고 하는 경우 예측에 사용할 수 있지만, [!DNL People-Based Destinations]은 이메일 주소를 제공했지만 웹 사이트를 방문하지 않은 기존 고객을 타겟팅하는 데 도움이 될 수 있습니다.

**[!DNL People-Based Destinations]과(와) [!DNL Facebook] 통합에서 더 이상 자격이 없는 사용자를 대상에서 제외시킬 수 있습니까?**

예. 통합은 [!DNL Facebook] 대상자가 더 이상 해당 대상자에 적합하지 않을 때 해당 대상자에서 사용자를 제거할 수 있도록 지원합니다.
