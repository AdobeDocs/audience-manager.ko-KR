---
description: 프로필 링크 장치 그래프를 통한 세그먼트 리타겟팅 및 개인화된 세그먼트 자격에 대한 Recommendations 및 사용 사례.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: 프로필 링크 장치 그래프 사용 사례
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 8%

---

# 프로필 링크 장치 그래프 사용 사례 {#profile-link-device-graph-use-cases}

Recommendations 및 을 통한 세그먼트 리타겟팅 및 개인화된 세그먼트 자격에 대한 사용 사례 [!UICONTROL Profile Link Device Graph].

## 권장 사항 {#recommendations}

다음을 고려하십시오. [!UICONTROL Profile Link] 다음을 수행하는 캠페인용 device graph:

* 디지털 속성 전체에 걸쳐 높은 수준의 인증을 제공합니다. 사용 [외부 장치 그래프 옵션](merge-rule-definitions.md#device-options) 인증된 사용자가 소량인 경우.
* 알려진 대상을 정확하게 타깃팅해야 합니다. 다음 [!UICONTROL Profile Link Device Graph] 은 퍼스트 파티 인증된 데이터를 사용하여 빌드됩니다.
* 인증된 상태와 인증되지 않은 상태의 알려진 대상을 실시간으로 Target

![](assets/merge-rule-triangle2.png)

## 크로스 디바이스 타기팅 {#cross-device-personalization}

존이 휴가 패키지 상품을 검색하기 위해 정기적으로 사용하는 3개의 기기를 소유하고 있다고 가정해 보자: 그의 노트북 ([!DNL Device 1]), 그의 스마트폰 ([!DNL Device 2]) 및 태블릿([!DNL Device 3]). 그러나 John은 자신의 디바이스를 사용하여 패키지 거래의 여러 항목을 검색합니다.

* 노트북으로 항공편을 조회한다.
* 그는 스마트폰을 이용해 호텔을 찾는다.
* 그는 태블릿을 이용해 가이드 투어를 찾는다.

John이 위에 언급된 장치 세 개 모두에서 인증되지 않은 경우에도 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** 규칙: 휴일 패키지 공급자는 세 개의 장치 모두에서 마지막으로 인증한 사람이라고 가정하고 이러한 장치를 John의 인증된 프로필에 연결할 수 있습니다.

![마지막 장치 그래프](assets/last-device-graph.png)

Audience Manager은 프로필 병합에 참여한 모든 장치 프로필을 세그먼트에 대해 정규화하기 때문에 세 장치 프로필이 모두 세그먼트화됩니다. 다음 [!UICONTROL Profile Link Device Graph] 는 Audience Manager이 세 개의 장치 모두에서 동작을 보고 단일 장치 프로필이 단독으로 자격을 얻지 못하는 세그먼트에 대해 모든 장치를 자격을 부여할 수 있도록 합니다.

이 [!UICONTROL Profile Merge Rule] 마케터는 개별 장치 활동 대신 사용자 활동을 기반으로 한 한 사람이 소유한 모든 장치에 일관된 경험을 전달할 수 있습니다.

![크로스 디바이스 개인화](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [외부 장치 그래프 사용 사례](external-graph-use-cases.md)
>* [프로필 병합 규칙에 대한 일반 사용 사례](merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

