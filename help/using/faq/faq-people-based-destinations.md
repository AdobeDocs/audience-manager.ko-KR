---
description: '사람 기반 대상에 대한 일반적인 질문에 대한 답변입니다.  '
seo-description: '사람 기반 대상에 대한 일반적인 질문에 대한 답변입니다.  '
seo-title: People-based destinations FAQ
solution: Audience Manager
title: People-based destinations FAQ
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# People-based destinations FAQ {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Audience Manager 계정에 표시되지[!DNL People-Based Destinations]않습니다. 가용성에 대해 알아야 하는 것은 무엇입니까?**

[!DNL People-Based Destinations] 는 구매 시 제공되는 Premium Audience Manager 기능입니다. 가격 및 가용성에 대한 자세한 내용은 Adobe 세일즈 담당자에게 문의하십시오.

## 데이터 온보드 {#data-onboarding}

**고객 이메일 주소를 Audience Manager로 가져와서 사용할 수 있는 방법은[!DNL People-Based Destinations]무엇입니까?**

다음 두 가지 방법으로 오프라인 데이터를 Audience Manager로 가져올 [!DNL People-Based Destinations]수 있습니다.

* **파일 기반 ID 동기화**&#x200B;사용 ID [동기화 파일에 대한 자세한 내용은 ID 동기화 파일에](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 대한 이름 및 컨텐츠 요구 사항을 참조하십시오. 이 방법을 사용하는 경우 [!DNL CRM] 데이터베이스에서 해시된 모든 이메일 주소를 타깃팅할 수 있습니다.
* **인증된 고객 ID를 전달할 때 선언된 ID** 를 사용하여 해시된 이메일 주소를 선언합니다. 이 방법을 사용할 경우 Audience Manager는 온라인으로 인증된 사용자의 해시된 이메일 주소만 활성화합니다. Facebook를 통해 활성화된 이메일 주소는 선언된 ID 이벤트 호출의 이메일 주소입니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 활성화되지 않습니다.

**웹 양식 또는 모바일 앱을 통해 해시된 이메일 주소를 수집할 수 있습니까? 아니면 일괄 처리 파일로 이동해야 합니까?**

선언된 ID [!DNL ECID] 를 사용하여 [웹 인증을 통해 해시된 이메일 주소를 수집할](../features/declared-ids.md)수 있습니다. 일괄 처리 파일을 사용하면 인증을 통해 전송할 수 없는 해시된 이메일 주소 (예: ([!DNL CRM]() 의 유휴 사용자) 를 수집하고 사용자 기반 대상에 활성화할 수도 있습니다.

**해시 이메일을 통해 해시된 이메일 주소를 업로드하지 않고도 웹 양식을 통해 해시된 이메일 주소를 수집하는 방법은 무엇입니까?**

오프라인 데이터 통합은 인증 없이 사용 사례를 지원하도록 설계되었으며[!UICONTROL All Cross-Device Profiles], 인증에 관계없이 모든 오프라인 [!DNL CRM] 프로필에서 실행되는 새 프로필 병합 규칙 () 를의 일부로 사용할 수 [!DNL People-Based Destinations]있습니다. 이 방법은 온라인 소스에서 인증된 대상자의 인제스트를 보완하기 위한 것입니다.

**해시된 이메일 주소를 전송/업데이트할 수 있는 최대 빈도는 어느 정도입니까?**

* 선언된 ID를 사용할 때 Audience Manager는 해시된 이메일 주소를 대상에 실시간으로 보냅니다.
* Adobe Audience Manager는 ID 동기화 파일을 통해 데이터를 인제스트할 때 매일 처리합니다.

**이메일 주소 해싱이 올바르게 완료되었는지 어떻게 알 수 있습니까?**

Audience Manager는 원시 이메일 주소를 인제스트하지 않고 있으며 해시가 올바르게 수행되었는지 확인할 수 없습니다. 온보드 데이터의 해시 해지를 위한 자세한 내용은 [사전 요구 사항 및 고려 사항을](../features/destinations/people-based-destinations-prerequisites.md) 참조하십시오.

## 프로필 병합 규칙 {#profile-merge-rules}

**사용할 수 있는 새 프로필 병합 규칙이 있습니까[!DNL People-Based Destinations]?**

예. 구매한 [!DNL People-Based Destinations] 고객은 오프라인 세그멘테이션을 위한 새로운 프로필 병합 규칙에 대한 액세스 권한을 부여받습니다. 규칙이 호출되고 [!DNL All Cross-Device Profiles] 오프라인 전용 세그멘테이션에 사용됩니다. 등록할 [!DNL People-Based Destinations]때 세 개의 기존 인증 기반 규칙 이외에 만들 수 있는 네 번째 프로필 병합 규칙입니다.

**기존 대상 세그먼트를 복제하여 활성화해야[!DNL People-Based Destinations]합니까?**

사용 사례에 따라 다릅니다. 사용자 기반 채널에서 기존 퍼스트 파티 세그먼트를 활성화할 계획이라면 새 세그먼트를 만들 필요가 없습니다. 세그먼트를 사람 기반 대상에 매핑할 수만 있습니다.

사람 기반 채널에서 새 오프라인 대상을 활성화할 계획인 경우 [!DNL All Cross-Device Profiles] 병합 규칙을 사용하여 새 자사 세그먼트를 만들어야 합니다.
>[!NOTE]
>
> 자사 데이터가 있는 세그먼트만 매핑할 [!DNL People-Based Destinations]수 있습니다. Adobe의 대상 플랫폼은 제휴 데이터와 제 3 자 데이터가 포함된 세그먼트를 허용하지 않습니다.

## 일치 비율 {#match-rates}

**일치[!DNL People-Based Destinations]비율이나 지정 가능 고객에 대한 가시성이 있습니까?**

아니요. 대상 세그먼트를 보낼 때 [!DNL People-Based Destinations]대상 일치가 파트너 측에서 발생합니다. Adobe는 이러한 지표에 액세스할 수 없습니다. Audience Manager는 각 대상에 대해 최대 공유 가능한 대상과 세그먼트에 속하는 사람들의 실시간 수를 보여줍니다. 이 정보는 캠페인 계획 및 예측을 도와줄 수 있습니다.

**대상 플랫폼으로 대상을 전송하는 다른 방법과[!DNL People-Based Destinations]이론적으로 비교하는 비율은 어떻게 됩니까?**

이메일 주소가 해싱되고 올바르게 인제스트되는 한, 간 [!DNL People-Based Destinations] 일치 비율과 다른 방법 간에는 차이가 없어야 합니다. 일치 비율이 100% 미만인 유일한 원인은 Audience Manager로 가져온 이메일 주소가 대상 플랫폼의 사용자 기반 이메일 주소와 일치할 수 없는 경우입니다.

**고객으로부터 직장 이메일 주소를 수집합니다. 이 주소는 소셜 네트워크에서 사용되는 개인 이메일 주소와 다릅니다. 여러 이메일 주소의 ID를 어떻게 일치시킬 수 있습니까?**

Audience Manager는 사용자당 최대 10 개의 이메일을 수집하여 대상 플랫폼에 보낼 수 있지만, 동기화 파일을 통해 이메일 주소를 캡처해야 합니다. Audience Manager가 이메일 주소를 대상 플랫폼에 보낸 후 해당 사용자 기반에서 이메일 주소와 일치하는 플랫폼까지 표시됩니다. 일부 플랫폼에는 Audience Manager에서 사용자 프로필에 보낸 주소와 일치하는 추가 이메일 주소 그래프가 있을 수 있습니다.

## 데이터 내보내기 제어 {#data-export-controls}

**[!DNL Data Export Controls][!DNL People-Based Destinations]사용 방법**

[!DNL Data Export Controls] 사용자가 보내려는 두 번째 및 타사 데이터가 들어 [!DNL People-Based Destinations]있는 세그먼트를 차단합니다. [!DNL People-Based Destinations] 타깃팅을 위해 퍼스트 파티 데이터만 사용할 수 있습니다. [!DNL Data Export Controls] 장치 그래프를 [!DNL Profile Merge Rules] 사용하여 세그먼트를 차단합니다. [!DNL People-Based Destinations] 해당 데이터 내보내기 레이블이 선택되어 있고 내보내기 설정을 덮어쓸 수 없습니다.

## 파트너 관련 질문 {#partner-specific-questions}

### [!DNL Facebook]

**대상 세그먼트를 보내려면 먼저 어떻게 해야[!DNL Facebook]합니까?**

대상 세그먼트를 [!DNL People-Based Destinations] 으로 [!DNL Facebook]전송하는 데 사용하려면 먼저 다음 구성 작업을 수행해야 합니다.

1. Adobe Experience Cloud 비즈니스 계정을 [!DNL Facebook Ad Account]광고 파트너로 추가합니다. 활동을 만들려면 `business ID=206617933627973`. 자세한 내용은 비즈니스 관리자에게 파트너 추가를 참조하십시오.

   >[!IMPORTANT]
   >
   > Adobe Experience Cloud에 대한 권한을 구성할 때 캠페인 관리 권한을 활성화해야 합니다. 통합을 위해 [!DNL People-Based Destinations] 필요합니다.

1. 을 읽고 [!DNL Facebook Custom Audiences Terms of Service]서명합니다. 이 작업을 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]``accountID`[!DNL Facebook Ad Account ID]수행하려면 어디에서나 이동하십시오.

**다른 앱에서 대상 타깃팅을[!DNL People-Based Destinations][!DNL Facebook]지원합니까[!DNL Instagram]?**

, 를 포함하여, 에서 지원하는 [!DNL People-Based Destinations] 모든 앱 [!DNL Facebook]제품군을 [!DNL Custom Audiences]사용할 [!DNL Facebook][!DNL Instagram][!DNL Audience Network][!DNL Messenger]수 있습니다. 캠페인을 실행할 앱의 선택은의 배치 수준에서 표시됩니다 [!DNL Facebook Ads Manager].

**[!DNL People-Based Destinations][!DNL Website Custom Audiences]와의 차이점은 무엇입니까?**

[!DNL People-Based Destinations][!DNL Custom Audiences (CA)] 와의 통합을 활용합니다 [!DNL Facebook]. 통합과 통합은 [!DNL WCA] 고객이 대상을 [!DNL CA] 보낼 때 사용하는 핵심 [!DNL Facebook]요소입니다. [!DNL WCA] 통합된 이메일 주소를 사용하는 동안 [!DNL Facebook][!DNL People-Based Destinations] 픽셀 (웹 사이트 사용자 ID) 를 사용합니다 [!DNL CA].

추가 비용 없이 기능을 통해 Audience Manager [!DNL Facebook][!DNL WCA] 의 통합을 [!DNL URL Destinations] 사용할 수 있습니다.

이러한 두 가지 통합은 보완적입니다. 두 가지 모두를 사용하여 더 나은 고객 범위를 유지할 수 있습니다. 예를 들어, 회사가 계정을 등록하지 않은 웹 사이트 방문자를 타깃팅하려는 경우 이를 구상하는 데 사용할 [!DNL WCA] 수 있으며, 반면에 [!DNL People-Based Destinations] 이메일 주소를 제공했지만 웹 사이트를 방문하지 않은 기존 고객을 타깃팅하는 데 도움이 될 수 있습니다.
