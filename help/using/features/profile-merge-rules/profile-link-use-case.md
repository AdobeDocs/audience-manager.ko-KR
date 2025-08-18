---
description: 프로필 링크 장치 그래프를 통한 세그먼트 리타겟팅 및 개인화된 세그먼트 자격에 대한 권장 사항 및 사용 사례.
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
ht-degree: 4%

---

# 프로필 링크 장치 그래프 사용 사례 {#profile-link-device-graph-use-cases}

[!UICONTROL Profile Link Device Graph]을(를) 통한 세그먼트 리타겟팅 및 개인화된 세그먼트 자격에 대한 권장 사항 및 사용 사례입니다.

## 권장 사항 {#recommendations}

다음과 같은 캠페인에 대한 [!UICONTROL Profile Link] 장치 그래프를 고려하십시오.

* 디지털 속성 전체에 걸쳐 높은 수준의 인증을 제공합니다. 인증된 사용자가 적은 경우 [외부 장치 그래프 옵션](merge-rule-definitions.md#device-options)을 사용하십시오.
* 알려진 대상을 정확하게 타깃팅해야 합니다. [!UICONTROL Profile Link Device Graph]은(는) 인증된 자사 데이터를 사용하여 빌드됩니다.
* 인증된 상태와 인증되지 않은 상태의 알려진 대상을 실시간으로 타깃팅합니다.

![](assets/merge-rule-triangle2.png)

## 크로스 디바이스 타기팅 {#cross-device-personalization}

존이 휴일 패키지 거래를 검색하기 위해 정기적으로 사용하는 장치를 세 개 보유하고 있다고 가정해 보겠습니다.: 그의 노트북([!DNL Device 1]), 그의 스마트폰([!DNL Device 2]), 그리고 그의 태블릿([!DNL Device 3]). 그러나 John은 자신의 디바이스를 사용하여 패키지 거래의 여러 항목을 검색합니다.

* 노트북으로 항공편을 조회한다.
* 그는 스마트폰을 이용해 호텔을 찾는다.
* 그는 태블릿을 이용해 가이드 투어를 찾는다.

John이 위에 언급된 장치 세 개 모두에서 인증되지 않았더라도 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** 규칙을 사용하여 휴일 패키지 공급자는 John이 세 개의 장치 모두에서 인증한 마지막 사람이었다고 가정할 때 이러한 장치를 John의 인증된 프로필에 연결할 수 있습니다.

![마지막 장치 그래프](assets/last-device-graph.png)

Audience Manager은 프로필 병합에 참여한 모든 장치 프로필을 세그먼트에 자격을 부여하므로 세 장치 프로필이 모두 세그먼트화됩니다. [!UICONTROL Profile Link Device Graph]을(를) 사용하면 Audience Manager에서 세 개의 장치 모두에서 동작을 보고 단일 장치 프로필이 단독으로 사용할 수 없는 세그먼트에 대해 모든 장치를 사용할 수 있습니다.

이 [!UICONTROL Profile Merge Rule]을(를) 사용하면 마케터가 개별 장치 활동 대신 사용자 활동을 기반으로 한 한 사람이 소유한 모든 장치에 일관된 환경을 제공할 수 있습니다.

![장치 간 개인화](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [외부 장치 그래프 사용 사례](external-graph-use-cases.md)
>* [프로필 병합 규칙에 대한 일반 사용 사례](merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)
