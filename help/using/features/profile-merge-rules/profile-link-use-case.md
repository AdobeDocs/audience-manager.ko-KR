---
description: 프로필 링크 장치 그래프를 사용하여 세그먼트 재타깃팅 및 개인화된 세그먼트 자격 검증을 위한 권장 사항 및 사용 사례
seo-description: 프로필 링크 장치 그래프를 사용하여 세그먼트 재타깃팅 및 개인화된 세그먼트 자격 검증을 위한 권장 사항 및 사용 사례
seo-title: 프로필 링크 장치 그래프 사용 사례
solution: Audience Manager
title: 프로필 링크 장치 그래프 사용 사례
uuid: bd5567fd-fcd5-40ba-b6f1-035d2dbcd3a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 프로필 링크 장치 그래프 사용 사례 {#profile-link-device-graph-use-cases}

세그먼트 재타깃팅 및 세그먼트 자격 검증을 위한 권장 사항 및 사용 사례를 [!UICONTROL Profile Link Device Graph]참조하십시오.

## 권장 사항 {#recommendations}

다음의 캠페인에 대한 [!UICONTROL Profile Link] 장치 그래프를 고려하십시오.

* 디지털 속성 전반에 걸쳐 높은 수준의 인증을 받을 수 있습니다. 인증된 사용자의 수가 적은 경우 [외부 장치 그래프 옵션을](merge-rule-definitions.md#device-options) 사용합니다.
* 알려진 고객을 정확하게 타깃팅해야 합니다. 이 [!UICONTROL Profile Link Device Graph] 파일은 인증된 퍼스트 파티 데이터를 사용하여 만들어집니다.
* 인증된 상태와 인증되지 않은 상태에 있는 알려진 고객을 실시간으로 타깃팅합니다.

![](assets/merge-rule-triangle2.png)

## 크로스 디바이스 타깃팅 {#cross-device-personalization}

John이 휴일 패키지 거래를 찾기 위해 정기적으로 사용하는 세 개의 장치를 가지고 있다고 가정해 봅시다.노트북([!DNL Device 1]), 스마트폰([!DNL Device 2]) 및 태블릿([!DNL Device 3]). 그러나 John은 그의 장치를 사용하여 패키지 거래의 다른 항목을 검색합니다.

* 그는 자신의 노트북을 비행기 검색을 이용한다.
* 호텔을 찾기 위해 스마트폰을 사용합니다.
* 그는 자신의 태블릿을 사용하여 가이드 투어를 검색합니다.

John이 위에 언급된 세 장치 모두에서 인증되지 않더라도, **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** 규칙을 사용하여 휴일 패키지 제공자는 John이 세 장치 모두에서 인증한 마지막 사람이었다고 가정하고 이러한 장치를 John의 인증된 프로필에 연결할 수 있습니다.

![last-device-graph](assets/last-device-graph.png)

Audience Manager는 세그먼트에 대해 프로필 병합에 참여한 모든 장치 프로필을 검사하므로 세 장치 프로필이 모두 세그먼트화됩니다. Audience Manager [!UICONTROL Profile Link Device Graph] 를 사용하면 세 장치 모두에서 동작을 확인하고 단일 장치 프로필이 자체적으로 받을 수 없는 세그먼트에 대한 모든 장치를 평가할 수 있습니다.

이를 [!UICONTROL Profile Merge Rule] 통해 마케터는 개별 디바이스 활동이 아닌 사용자 활동에 따라 한 사람이 소유한 모든 디바이스에 일관된 경험을 제공할 수 있습니다.

![크로스 디바이스 개인화](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [외부 장치 그래프 사용 사례](external-graph-use-cases.md)
>* [프로필 병합 규칙에 대한 일반 사용 사례](merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

