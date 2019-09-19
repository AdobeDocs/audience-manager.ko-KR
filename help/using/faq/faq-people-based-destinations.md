---
description: '사람 기반 대상에 대한 일반적인 질문에 대한 답변입니다.  '
seo-description: '사람 기반 대상에 대한 일반적인 질문에 대한 답변입니다.  '
seo-title: 사람 기반 대상 FAQ
solution: Audience Manager
title: 사람 기반 대상 FAQ
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 사람 기반 대상 FAQ {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Audience Manager[!DNL People-Based Destinations]계정에 없습니다. 가용성에 대해 무엇을 알아야 합니까?**

[!DNL People-Based Destinations] 는 구입 시 사용할 수 있는 프리미엄 Audience Manager 기능입니다. 가격 및 가용성에 대한 자세한 내용은 Adobe 세일즈 담당자에게 문의하십시오.

## 데이터 온보딩 {#data-onboarding}

**고객 이메일 주소를 Audience Manager에 게시하여 사용할 수 있는 방법은[!DNL People-Based Destinations]무엇입니까?**

두 가지 방법으로 Audience Manager에 오프라인 데이터를 가져올 수 [!DNL People-Based Destinations]있습니다.

* **파일 기반 ID 동기화**&#x200B;사용 ID [동기화 파일의 모양에 대한 자세한](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 내용은 ID 동기화 파일의 이름 및 컨텐츠 요구 사항을 참조하십시오. 이 방법을 사용하는 경우 [!DNL CRM] 데이터베이스에서 해시된 모든 이메일 주소를 타깃팅할 수 있습니다.
* **인증된 고객 ID를 전달할** 때 선언된 ID를 사용하여 해시된 이메일 주소를 선언합니다. 이 방법을 사용하는 경우 Audience Manager는 온라인에서 인증된 사용자의 해시된 이메일 주소만 활성화합니다. Facebook을 통해 활성화된 이메일 주소는 선언된 ID 이벤트 호출에 있는 이메일 주소만 해당됩니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 활성화되지 않습니다.

**해시된 이메일 주소를 웹 양식 또는 모바일 앱을 통해 수집할 수 있습니까? 아니면 일괄 처리 파일을 통해 수신해야 합니까?**

선언된 ID를 사용하여 웹 인증을 통해 해시된 이메일 주소를 수집할 [!DNL ECID] 수 [있습니다](../features/declared-ids.md). 또한 일괄 처리 파일을 사용하면 인증을 통해 전송할 수 없는 해시 이메일 주소(예: 사용자([!DNL CRM])에 있는 비활성 사용자 및 사람 기반 대상의 활성화를 수행할 수 있습니다.

**해시된 이메일 주소를 웹 양식을 통해 인제스트하는 것과 일괄 처리 파일을 통해 해시된 이메일 주소를 업로드하는 것과 어떻게 다릅니까?**

오프라인 데이터 수집은 인증 없이 사용 사례를 지원하기 위해 고안되었으며, 인증과 관계없이 모든 오프라인[!UICONTROL All Cross-Device Profiles]프로파일에서 실행되는 새로운 프로필 병합 규칙( [!DNL CRM] )을 [!DNL People-Based Destinations]의 일부로 사용할 수 있습니다. 이 방법은 온라인 소스에서 인증된 대상을 수집하도록 하기 위한 것입니다.

**해시된 이메일 주소를 전송/업데이트할 수 있는 최대 빈도는 무엇입니까?**

* 선언된 ID를 사용할 때 Audience Manager는 해시된 이메일 주소를 대상으로 실시간으로 보냅니다.
* ID 동기화 파일을 통해 데이터를 인제스트할 때 Audience Manager는 매일 데이터를 처리합니다.

**이메일 주소 해시가 올바르게 수행되었는지 어떻게 알 수 있습니까?**

Audience Manager가 원시 이메일 주소를 인제스트하고 있지 않으므로 해시가 올바르게 수행되었는지 확인할 수 없습니다. 온보드 [데이터를](../features/destinations/people-based-destinations-prerequisites.md) 해시하는 방법에 대한 자세한 내용은 사전 요구 사항 및 고려 사항을 참조하십시오.

## 프로필 병합 규칙 {#profile-merge-rules}

**사용할 수 있는 새 프로필 병합 규칙이[!DNL People-Based Destinations]있습니까?**

예. 구매한 고객은 오프라인 세그멘테이션을 위해 새 프로필 병합 규칙에 액세스할 [!DNL People-Based Destinations] 수 있습니다. 규칙이 호출되고 [!DNL All Cross-Device Profiles] 오프라인 전용 세그멘테이션에 사용됩니다. 등록하면 세 개의 기존 인증 기반 규칙 외에 만들 수 있는 네 번째 프로필 병합 규칙입니다. [!DNL People-Based Destinations]

**기존 대상 세그먼트를 복제하여 활성화해야[!DNL People-Based Destinations]합니까?**

사용 사례에 따라 다릅니다. 사람 기반 채널에서 기존 자사 세그먼트를 활성화할 계획이라면 새 세그먼트를 만들 필요가 없습니다. 세그먼트를 사람 기반 대상에 매핑할 수 있습니다.

사람 기반 채널에서 새 오프라인 대상을 활성화하려는 경우 병합 규칙을 사용하여 새 퍼스트 파티 세그먼트를 만들어야 합니다. [!DNL All Cross-Device Profiles]
>[!NOTE]
>
> 퍼스트 파티 데이터가 있는 세그먼트만 매핑할 수 [!DNL People-Based Destinations]있습니다. Adobe의 대상 플랫폼은 제2자 및 제3자 데이터가 있는 세그먼트를 허용하지 않습니다.

## 일치 비율 {#match-rates}

**일치율 또는 어드레서블 대상의 가시성이[!DNL People-Based Destinations]있습니까?**

아니요. 대상 세그먼트를 대상 세그먼트에 보낼 [!DNL People-Based Destinations]때 파트너 측에서 고객 일치를 수행합니다. Adobe는 해당 지표에 대한 액세스 권한을 가지고 있지 않습니다. Audience Manager는 각 대상에 대한 공유 가능한 최대 대상 및 세그먼트에 속하는 사람들의 실시간 수를 보여줍니다. 이 정보는 캠페인 계획 및 예측에 도움이 될 수 있습니다.

**대상 플랫폼으로 고객을 보내는 다른 방법과[!DNL People-Based Destinations]이론적으로 비교하면서 어떻게 비율을 일치시킬 수 있습니까?**

이메일 주소가 올바로 해시되고 인제스트된 경우, [!DNL People-Based Destinations] 및 기타 메서드 간의 일치율에는 차이가 없습니다. 일치 비율이 100% 미만이 되는 유일한 이유는 Audience Manager로 가져온 이메일 주소가 대상 플랫폼의 사용자 기반에 있는 이메일 주소와 일치하지 않는 경우입니다.

**소셜 네트워크에 사용되는 개인 이메일 주소와 다른 이메일 주소를 고객으로부터 수집합니다. 여러 이메일 주소에서 ID를 어떻게 일치시키십니까?**

Audience Manager는 사용자당 최대 10개의 이메일을 수집하고 대상 플랫폼에 보낼 수 있지만 동기화 파일을 통해 이메일 주소를 캡처해야 합니다. Audience Manager가 대상 플랫폼에 이메일 주소를 전송하면 해당 이메일 주소가 사용자 기반과 일치할 수 있는 플랫폼이 결정됩니다. 일부 플랫폼에는 Audience Manager에서 사용자 프로필로 보낸 주소와 일치하도록 추가 이메일 주소 그래프가 있을 수 있습니다.

## 데이터 내보내기 제어 {#data-export-controls}

**어떻게[!DNL Data Export Controls]작업합니까[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] 는 사용자가 전송하려고 [!DNL People-Based Destinations]하는 제휴 데이터와 제3자 데이터가 포함된 모든 세그먼트를 차단합니다. [!DNL People-Based Destinations] 퍼스트 파티 데이터만 타깃팅에 사용할 수 있습니다. [!DNL Data Export Controls] 또한 장치 그래프와 [!DNL Profile Merge Rules] 함께 사용하여 세그먼트를 차단합니다. [!DNL People-Based Destinations] 적절한 데이터 내보내기 레이블이 선택된 상태로 작성되며 내보내기 설정을 덮어쓸 수 없습니다.

## 파트너 관련 질문 {#partner-specific-questions}

### [!DNL Facebook]

**대상 세그먼트를 보낼 수 있으려면 어떻게 해야[!DNL Facebook]합니까?**

를 사용하여 대상 세그먼트를 [!DNL People-Based Destinations] 다음으로 보내려면 [!DNL Facebook]먼저 다음 구성 작업을 수행해야 합니다.

1. Adobe Experience Cloud 비즈니스 계정을 광고 파트너로 [!DNL Facebook Ad Account]추가합니다. 활동을 만들려면 `business ID=206617933627973`. 자세한 내용은 비즈니스 관리자에 파트너 추가를 참조하십시오.

   >[!IMPORTANT]
   >
   > Adobe Experience Cloud에 대한 권한을 구성할 때 캠페인 관리 권한을 활성화해야 합니다. 이 작업은 [!DNL People-Based Destinations] 통합에 필요합니다.

1. 문서를 읽고 서명합니다 [!DNL Facebook Custom Audiences Terms of Service]. 이렇게 하려면, `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`어디로 `accountID` 가십시오 [!DNL Facebook Ad Account ID].

**다른 앱의 고객 타깃팅을[!DNL People-Based Destinations]지원합니까, 예:[!DNL Facebook][!DNL Instagram]?**

[!DNL People-Based Destinations] 및 [!DNL Facebook]를 비롯하여, 에서 지원하는 모든 앱 제품군을 사용할 [!DNL Custom Audiences]수 [!DNL Facebook][!DNL Instagram][!DNL Audience Network] [!DNL Messenger]있습니다. 캠페인을 실행할 앱 선택은 의 배치 수준에서 [!DNL Facebook Ads Manager]표시됩니다.

**와 의 차이점은[!DNL People-Based Destinations]무엇인가요[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] 를 사용하여 [!DNL Custom Audiences (CA)] 통합을 [!DNL Facebook]수행합니다. 고객을 [!DNL WCA] 보낼 때 고객이 사용하는 핵심 요소는 [!DNL CA] 통합과 통합의 차이입니다 [!DNL Facebook]. [!DNL WCA] 는 [!DNL Facebook] 픽셀(웹 사이트 사용자 ID일 수)을 사용하는 동시에 해시된 이메일 주소를 사용하여 [!DNL People-Based Destinations] [!DNL CA]와 통합합니다.

추가 비용 없이 이 기능을 통해 Audience Manager의 [!DNL Facebook][!DNL WCA] 통합을 사용할 수 [!DNL URL Destinations] 있습니다.

이러한 두 가지 통합은 상호 보완적입니다.두 가지 모두를 사용하여 고객 범위를 개선할 수 있습니다. 예를 들어, 회사가 계정을 등록하지 않은 웹 사이트 방문자를 타게팅하려고 할 때 잠재 고객 확보에 사용할 [!DNL WCA] 수 있지만, 이메일 주소를 제공했지만 웹 사이트를 방문하지 않은 기존 고객을 타게팅하는 [!DNL People-Based Destinations] 데 도움이 될 수 있습니다.
